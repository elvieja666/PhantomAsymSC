# Phantom Asym (sidechain only)

Silencia el audio que entra, en full range, siguiendo los cycles de la señal que le mandes por el **sidechain input**.

## Controles

| Control | Qué hace |
|---|---|
| **Depth** | Cuánto baja el audio (100 % = silence total) |
| **Mode** | **1 cycle yes / 1 no**: silencia un cycle completo, deja pasar el siguiente, y así alternando. **Half-wave**: silencia un solo semiciclo de cada cycle |
| **First Cycle** | En cada golpe, si el primer cycle se silencia (**Silence**) o pasa (**Pass**) |
| **Polarity** | Dónde empieza cada cycle: semiciclo positivo o negativo |
| **Output** | Volumen final |

## Cómo usarlo

1. Poné Phantom Asym en la pista (o el master) que querés afectar.
2. Mandá al **sidechain input** una señal con solo el **sub** (por ejemplo, un kick o un 808 filtrado). El plugin no tiene filtros internos: si le mandás una señal con medios y agudos, va a detectar cycles de más. Filtrá el low end en la pista que mandás al sidechain.
3. Sin señal en el sidechain, el audio pasa sin cambios.

## Notas

- Solo atenúa, nunca amplifica. No tiene latency ni filtros en el camino del audio.
- El sidechain se detecta en mono (promedio de L y R) y la misma bajada se aplica a todos los canales.
- Cuando el sidechain se apaga (entre golpes), el contador se reinicia y cada golpe arranca igual.

## Compilar e instalar

1. Reemplazá los archivos de tu carpeta del proyecto por los de este zip.
2. En GitHub Desktop: escribí un Summary, **Commit to main**, **Push origin**.
3. Esperá la compilación en **Actions**, descargá el artifact de Windows o Mac.
4. Mac: `.vst3` a `~/Library/Audio/Plug-Ins/VST3/` y `.component` a `~/Library/Audio/Plug-Ins/Components/`, después `xattr -cr` sobre cada uno.
   Windows: `.vst3` a `C:\Program Files\Common Files\VST3\`
