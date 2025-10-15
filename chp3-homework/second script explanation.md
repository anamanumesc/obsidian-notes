Write a script that will start a small web server listening an unused port between `8000-9990` that will show new `top` command output every 10 seconds.

```bash

#!/usr/bin/env bash

# Find a free port between 8000 and 9990
PORT=""
for p in $(seq 8000 9990); do
#ss command 
  if ! ss -ltn 2>/dev/null | grep -q ":$p"; then #looks for ports
    PORT="$p"
    break
  fi
done
[ -z "$PORT" ] && PORT=8000

DIR="/tmp/topserver"
mkdir -p "$DIR"

# Update the page every 10s with fresh `top` output
update_page() {
  while true; do
    {
      echo '<!doctype html><html><head><meta charset="utf-8">'
      echo '<meta http-equiv="refresh" content="10"><title>top</title></head><body>'
      echo "<h3>top snapshot</h3><p>Updated: $(date '+%Y-%m-%d %H:%M:%S %Z')</p><pre>"
      top -b -n1
      echo '</pre></body></html>'
    } > "$DIR/index.html"
    sleep 10
  done
}

update_page & UP_PID=$!
trap 'kill "$UP_PID" 2>/dev/null' EXIT

cd "$DIR" || exit 1
echo "Serving http://$(hostname -I | awk "{print \$1}"):$PORT"
python3 -m http.server "$PORT"
```