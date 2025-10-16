Write a script that will start a small web server listening an unused port between `8000-9990` that will show new `top` command output every 10 seconds.

```bash
#!/usr/bin/env bash

DIR="/tmp/topserver"
mkdir -p "$DIR"

update_page() {
  while :; do
    {
      echo '<!doctype html><html><head><meta charset="utf-8">'
      echo '<meta http-equiv="refresh" content="10"><title>top</title></head><body>'
      echo '<h3>system top snapshot </h3><pre>'
      top -b -n1
      echo '</pre></body></html>'
    } > "$DIR/top.html"
    sleep 10
  done
}

update_page & UP_PID=$!
trap 'kill "$UP_PID" 2>/dev/null; exit' INT TERM EXIT #signals

cd "$DIR" || { echo "nu pot intra in $DIR" >&2; exit 1; }

for PORT in {8000..9990}; do
  echo "Trying http://127.0.0.1:$PORT"
  python3 -m http.server "$PORT" --bind 127.0.0.1 2>/dev/null
done

echo "No free port found in 8000-9990" >&2
exit 1


```


daca aveam mai multe fisiere unde le puneam?: Orice fișier HTML/JS/CSS pe care vrei să-l servești cu `python3 -m http.server` trebuie să fie **în directorul curent** de unde rulezi serverul sau în subfoldere.
