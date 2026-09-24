# Registro de cobertura acumulada — *El dispositivo caldereño*

Archivo exigido por CORRIGE 3.6 («Cobertura acumulada»). **Se versiona en el repositorio del libro**, no en la conversación. Cada ronda agrega su bloque; una línea leída dos veces cuenta una vez; al reescribir sustancialmente un archivo, sus tramos anteriores caducan y se marcan `caduco`.

- Manuscrito al abrir el registro: **24.476 líneas** en 38 archivos `.tex` (commit base de la ronda 35).
- Rondas 1–34: **sin registro en archivo → cobertura acumulada 0** por regla. Lo leído entonces no se reconstruye de memoria.

## Ronda 35 — auditoría (23/09/2026)

### Lectura sobre el texto

| Archivo | Líneas | Nota |
|---|---|---|
| cap/00-advertencia.tex | 43, 68–78 | 43 es un párrafo largo; leído entero |
| cap/01-planteo.tex | 135–141 | refutadores de las tres tesis |
| cap/02-metodo.tex | 28, 81 | |
| cap/04-siglo.tex | 430–435, 2172–2177, 2263–2268, 2385–2389, 2801–2805, 3012–3016, 3140–3144, 3391–3395, 3548–3562, 4397–4400 | |
| cap/11-ribera.tex | 1055–1062 | epígrafe `fig:catastro` |
| cap/15-hacienda.tex | 74–78 | |
| cap/18-politica.tex | 409–412 | |
| cap/20-opacidad.tex | 714–718, 730–733 | |
| cap/21-ausencias.tex | 70–75 | |
| cap/21-conclusion.tex | 80–85 | |
| cap/22-prospectiva.tex | 270–282 | |
| ape/D-pedidos.tex | 1–35, 213, 217, 222, 240–245, 249, 251, 297 | más los ítems 161, 163, 165, 166, 192, 214, 263 |
| ape/F-fuentes.tex | 25–30, 42, 49–51, 106–112, 143, 199 | 42 leída en parte (una línea de varias páginas) |
| ape/G-propuestas.tex | 1–30, 775–804 | |

**Total aproximado: 265 líneas de 24.476 (1,1 %).** Acumulado: **1,1 %**.

### Controles por script (no cuentan como lectura; se declaran con su denominador)

| Control | Denominador | Resultado |
|---|---|---|
| Superlativos (*único, primero, más antiguo, nunca, jamás…*) | 24.476/24.476 líneas | 584 coincidencias; 98 referidas al archivo; 36 revisadas en contexto |
| Menciones de ventana y de número de tramos | 24.476/24.476 | 8 menciones; 7 desactualizadas |
| Pedidos con objeto ya obtenido | 278/278 ítems | 26 con «ya se obtuvo»; 8 leídos; 1 con el objeto principal satisfecho |
| Pedidos duplicados por destinatario (número de expediente/ley) | 278/278 | 1 duplicado real (3898-C, cuatro menciones); 2 falsos positivos |
| Recuento de láminas en el texto frente al `.lof` | 38/38 entradas; 5 menciones del total | 4 menciones desfasadas (36 por 38) y 1 recuento de propias (15 por 17) |
| Estado de script de figuras propias | 17/17 | 11 publicados; 6 no publicados y declarados en F (uno con script ajeno en el epígrafe) |
| `\pendiente{}` con pedido del mismo capítulo | 52/52 | sin faltas |

## Ronda 36 — …
