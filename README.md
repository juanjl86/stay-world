# Stay World — demo de aventura 2D con chibi animado

Mini-juego/escena web en HTML5 canvas: un personaje **chibi** se mueve con las flechas o WASD
por un escenario y recoge estrellas ⭐.

El avatar **camina de verdad**: usa un ciclo de animación de 4 poses dibujadas, en las que
solo cambian piernas y brazos (mismo personaje, mismo tamaño y estilo en todos los frames).

## Cómo se hizo el avatar (lo importante)

Lo que **no** funciona:
- Pedirle a la IA una hoja con varias poses en las que cada una sale distinta → el personaje
  "late" (cambia de tamaño/forma entre frames).
- Recolorear a mano o blanquear píxeles sobre una silueta plana → la cara se ve lavada o rota.

Lo que **sí** funciona:
1. Generar el chibi **parado** (una sola imagen, bien dibujada de origen).
2. Usar esa imagen **como referencia** al pedir las poses de caminata → la IA mantiene el mismo
   personaje, solo cambian las piernas.
3. Para arreglar rasgos (p. ej. los ojos), **regenerar desde el prompt** en vez de parchear
   píxeles a mano.

## Estructura

```
index.html        # todo el juego (canvas + lógica + animación + selector)
img/<miembro>/    # hoja de caminata de cada uno (f0..f3.png = 4 poses)
  c4n/      -> Chan
  han/      -> Han
  hyunjin/  -> Hyunjin
  changbin/ -> Changbin
  felix/    -> Felix
  seungmin/ -> Seungmin
  in/       -> I.N
```

## Personajes

Puedes **elegir integrante en pantalla** con los chips de arriba; cada uno tiene su propia
hoja de caminata (mismo método: chibi de referencia -> 4 poses consistentes).

## Correr en local

Solo abrir `index.html` en el navegador, o servirlo:

```bash
python3 -m http.server 8080
# → http://localhost:8080
```

## Controles

- **Flechas / WASD** para moverte
- Recoge las ⭐

## Notas

Demo personal para uso no comercial. Los nombres de los personajes son referencias a
integrantes de Stray Kids (Chan, Han, Hyunjin).
