# Protocolo de Minería Narrativa — Documento Canónico
## El sistema de estrellas y la energía computacional como motor narrativo

---

## Las dos capas

El protocolo opera simultáneamente en dos niveles que comparten la misma física:

| Capa | Quién mina | Qué produce |
|---|---|---|
| **Intra-ficción** | Los personajes (queman Hash vital) | Transformaciones, poder, eventos del mundo |
| **Meta** | Lectores/comunidad (cómputo real: SHA-256, shares de Bitcoin, nodos del Caos Engine) | Ramas del DAG, capítulos ocultos, eventos, artefactos |

Principio rector: **lo que Dirk hace dentro de la ficción (minar energía de otro tiempo) es lo que el lector hace desde fuera (minar narrativa del universo).** El lector es un pequeño Dirk. La obra implica al lector en su propia crítica.

---

## 1. El sistema de estrellas (capa intra-ficción)

### Definición

El poder de un personaje se mide en **estrellas**, respaldadas por proof-of-work: para alcanzar un modo de N estrellas, se quemaron los hashes necesarios para encontrar esa dificultad.

```
hash = 000000f91a3b...
nivel de poder = número de ceros iniciales
```

### Propiedades de la escala

- **Exponencial por naturaleza**: cada estrella adicional es 16× más difícil que la anterior (base hexadecimal). Un 8 estrellas no es "un poco más" que un 7 — es un orden de magnitud más raro.
- **Verificable**: nadie puede declarar un nivel sin haber quemado el trabajo. En el universo, un personaje que dice ser 9 estrellas puede ser auditado — su Hash lo delata o lo confirma.
- **Sin techo teórico, con techo histórico**: siempre puede existir un hash con más ceros, pero **nadie en la historia registrada ha superado las 10 estrellas**. El modo 10 estrellas de Piggy representa una dificultad que costó una cantidad específica y enorme de hashes encontrar.
- **El costo es real**: minar poder consume al minero. Esta es la unificación con el canon de costos: Hiroshi debilita sus huesos, Eddy envejece, Piggy pierde identidad al digitalizarse. Cada transformación es trabajo quemado que no vuelve.

### Implicación anti-power-creep

La progresión de poder queda matemáticamente contenida: subir una estrella siempre cuesta 16× lo anterior. No hay "gritar más fuerte para ganar" — hay pagar la dificultad o no alcanzarla. Cuando en T3 alguien rompa el techo de 10, el costo narrativo debe ser proporcional a esa matemática: no un power-up, una catástrofe termodinámica.

---

## 2. Generación de eventos (ambas capas)

Los outputs de hash se decodifican como eventos narrativos:

```
byte[0] → sistema climático
byte[1] → spawn de criatura
byte[2] → rareza de objeto/artefacto
byte[3] → evento anómalo
```

Ejemplo:
```
hash: 3fa9b2c1...
clima = tormenta de plasma
spawn = criatura sombra
rareza = artefacto raro
```

Dentro de la ficción, esto es el "algoritmo de caos universal" que ya rige los Bloques (1 bloque ≈ 1 año): el mundo mismo corre sobre entropía minada. Fuera de la ficción, es el motor generativo de contenido para la comunidad.

---

## 3. Forks y el DAG (capa meta)

### Triggers por patrón

Patrones específicos en el hash disparan eventos de gravedad creciente. Propuesta de jerarquía (reservar patrones distintos para gravedades distintas):

| Patrón | Evento | Gravedad |
|---|---|---|
| `777` | Fork de rama narrativa (nueva rama del DAG, ej. `7-A-C`) | Mayor |
| `dd` (double-death) | Encuentro de jefe / amenaza | Media |
| `abc` secuencial | Artefacto / capítulo oculto | Media |
| `00` en byte final | Portal dimensional | Alta |

(Tabla ajustable — el principio es: rareza del patrón proporcional a la gravedad del evento.)

### Gobernanza del canon

- **El main-line es la cadena de mayor peso.** Solo el autor firma bloques en el main-line — es el genesis miner de la cadena principal.
- **Los forks comunitarios son ramas legítimas pero no canónicas** — como cadenas huérfanas de Bitcoin: existieron, tuvieron trabajo real invertido, se archivan en el DAG (`alt_storys/`), pero la cadena principal es la que el autor extiende.
- **Promoción de rama**: una rama comunitaria puede ser adoptada al canon por decisión del autor — el equivalente narrativo de un soft fork aceptado por la red.

### Espejo temático con T3

La Batalla de los Forks (T3) es esto mismo dentro de la ficción: dos cadenas de realidad compitiendo por ser la canónica, una condenada a colapsar como cadena huérfana. Green es la rama que se niega a ser huérfana. La estructura del protocolo ES la trama de T3.

---

## 4. Minería narrativa comunitaria

Los participantes aportan poder computacional para influir en el universo, buscando hashes que cumplan patrones específicos. Resultados posibles:

- Desbloquear capítulos ocultos
- Disparar encuentros de jefes
- Generar artefactos
- Abrir portales dimensionales

Fuentes de entropía: shares de minería de Bitcoin, iteración SHA-256 independiente, nodos de cómputo distribuido, red de entropía del Caos Engine. El universo de Block Jumper queda indirectamente alimentado por la minería de Bitcoin.

Esto materializa el objetivo de largo plazo de la obra: **que la comunidad continúe la cadena de bloques — la historia.**

---

## 5. Reglas de coherencia (guardrails editoriales)

1. **La entropía propone, el autor dispone.** Los eventos minados son materia prima narrativa, no obligaciones. Un evento generado que contradiga el canon se archiva como anomalía, no se fuerza.
2. **El costo siempre se paga.** Ningún personaje, comunidad o rama obtiene poder sin trabajo quemado verificable. Es la ley física y moral del universo — la violación de esta ley (Dirk) es precisamente el pecado original de la historia.
3. **Las estrellas no se heredan ni se regalan.** Se minan. La Conciencia compartida (linaje Blue) da acceso a experiencia, no a dificultad ya minada.
4. **Techo histórico: 10 estrellas.** Romperlo es un evento de temporada, no de capítulo.
