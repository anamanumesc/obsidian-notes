Write a script that will start a small web server listening an unused port between `8000-9990` that will show new `top` command output every 10 seconds.

```bash
#!/usr/bin/env bash
set -e

DIR="/tmp/topserver"
mkdir -p "$DIR"

# Regenerăm pagina la 10s cu un snapshot din `top`
update_page() {
  while :; do
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
IP=$(hostname -I 2>/dev/null | awk '{print $1}'); IP=${IP:-127.0.0.1}

for PORT in $(seq 8000 9990); do
  echo "Trying http://$IP:$PORT"
  # Dacă portul e ocupat, http.server iese cu eroare și bucla trece la următorul
  python3 -m http.server "$PORT" && exit 0
done

echo "No free port found in 8000-9990" >&2
exit 1

```
