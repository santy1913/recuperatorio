<p align="center"><img src="assets/escudo.png" alt="Escudo IPET 249" width="120"></p>

# Byte – Mascota Virtual de Informática

**Institución:** IPET 249 "Nicolás Copérnico"
**Especialidad:** Informática
**Asignatura:** Laboratorio de Aplicaciones II – 6° G
**Año:** 2026
**Alumno:** _[Nombre y apellido]_

---

## 1. Cómo ejecutar el juego

**En tu computadora**
1. Tener instalado Python 3.
2. Instalar pygame: `pip install pygame`
3. Ejecutar desde la carpeta del proyecto: `python mascota.py`

**Online, sin instalar nada**
1. Entrar a [onecompiler.com/pygame](https://onecompiler.com/pygame).
2. Pegar el contenido de `mascota_online.py` y apretar **Run**.

---

## 2. Jugabilidad

### Objetivo
Cuidar a **Byte**, un zorro programador, el mayor tiempo posible. No hay "game over": las barras nunca bajan de 0 ni suben de 100, pero cuanto más descuidado esté, peor se ve y se siente Byte. El desafío es mantener las tres barras en equilibrio.

### Las tres necesidades
Las tres barras bajan solas, todo el tiempo, mientras el juego está abierto.

| Barra | Representa | Baja por segundo | Tiempo hasta 0 (sin cuidarlo) |
|---|---|---|---|
| **Energía** | Carga de batería | 2,5 | 40 s |
| **Ánimo** | Nivel de código | 2 (3 si la energía es menor a 25) | 50 s (menos si está sin energía) |
| **Salud** | Limpio de bugs | 1,5 | ~67 s |

La barra se pone **roja** cuando queda por debajo de 25.

### Acciones
| Tecla | Botón | Qué hace |
|---|---|---|
| `C` | Tomar café | Energía **+25** |
| `J` | Programar | Energía **-15**, ánimo **+20**, salud **-5**. Byte teclea durante 2,5 segundos. **Necesita al menos 15 de energía**; si no, aparece "¡Sin batería! Dale un café primero" |
| `L` | Limpiar bugs | Salud **+25** |
| `R` | — | Reinicia a Byte con todas las barras al 100 |
| `ESC` | — | Sale del juego |

También se puede jugar con el mouse haciendo clic en los tres botones de abajo.

### Estados de Byte
Byte cambia de aspecto según cómo estén sus barras. Si se cumplen varias condiciones a la vez, gana la primera de esta lista:

| Prioridad | Estado | Cuándo aparece | Cómo se ve |
|---|---|---|---|
| 1 | **Programando** | Los 2,5 s después de apretar `J` | Teclea en su teclado y aparece una pantalla con código |
| 2 | **Cansado** | Energía menor a 25 | Ojos cerrados, bosteza y salen "zzz" |
| 3 | **Triste** | Ánimo menor a 30 o salud menor a 30 | Cejas caídas, mirada baja y una lágrima |
| 4 | **Feliz** | Todo lo demás | Saluda moviendo el brazo y las colas |

### Bugs en pantalla
Los bugs son los "enemigos" de Byte. Aparecen a medida que baja la salud: 1 bug cuando la salud llega a 80 o menos, y uno más cada 20 puntos hasta un máximo de 5. Al limpiar bugs, desaparecen a medida que sube la salud.

### Consejos
- Un café equivale a unos 10 segundos de desgaste de energía, así que no alcanza con tomar uno solo y olvidarse.
- Programar es la única forma de subir el ánimo, pero gasta energía y ensucia la salud. Conviene tomar café **antes** de programar y limpiar bugs **después**.
- Con la energía baja, el ánimo cae más rápido. Cuidá la energía primero.
- Si dejás todo bajar, Byte pasa a "cansado" a los ~30 s. Se queda en ese estado mientras la energía siga baja, aunque también esté triste: primero recargá energía y después mirá cómo están el ánimo y la salud.

---

## 3. Concepto de la mascota
Byte es un zorro de dos colas: un animal astuto y rápido, con un aspecto propio y fácil de recordar.

Para representar a **Informática** lleva anteojos, auriculares de gaming, un teclado y una pantalla con código, y sus barras hablan de batería, código y bugs.

Para representar al **IPET 249** usa los colores del colegio (**bordó, amarillo, rojo y blanco**): fondo bordó con una cuadrícula que recuerda a una placa de circuito, piso amarillo con franja blanca, buzo rojo con detalles amarillos y el logo "249". El **escudo del colegio** está siempre visible arriba a la izquierda.

## 4. Capturas
| Feliz | Programando |
|---|---|
| ![Feliz](capturas/feliz.png) | ![Programando](capturas/programando.png) |

| Cansado | Triste |
|---|---|
| ![Cansado](capturas/cansado.png) | ![Triste](capturas/triste.png) |

## 5. Estructura del repositorio
```
mascota.py          # programa principal
mascota_online.py   # misma versión en un solo archivo, para editores online
assets/escudo.png   # escudo del IPET 249
capturas/           # capturas de los 4 estados
GDD.md              # documento de diseño
IA_LOG.md           # ficha de transparencia del uso de IA
requirements.txt
```
