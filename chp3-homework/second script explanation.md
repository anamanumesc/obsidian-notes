Write a script that will start a small web server listening an unused port between `8000-9990` that will show new `top` command output every 10 seconds.

```bash
#!/usr/bin/env bash

DIR="/tmp/topserver"
mkdir -p "$DIR"

# 1) Generează pagina la fiecare 10s cu un snapshot din `top`
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

# pornește updater-ul în background și curăță la ieșire
update_page & UP_PID=$!
trap 'kill "$UP_PID" 2>/dev/null; exit' INT TERM EXIT

# 2) Servește directorul
cd "$DIR" || { echo "Nu pot intra în $DIR" >&2; exit 1; }

# Alegem primul port liber ÎNCERCÂND să pornim serverul (cel mai simplu)
for PORT in {8000..9990}; do
  echo "Trying http://127.0.0.1:$PORT"
  # Dacă portul e ocupat, http.server iese imediat și bucla continuă.
  # La primul port liber, comanda rămâne în prim-plan și servește pagina.
  python3 -m http.server "$PORT" --bind 127.0.0.1 2>/dev/null
done

echo "No free port found in 8000-9990" >&2
exit 1


```
