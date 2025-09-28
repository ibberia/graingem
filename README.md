graingem — tiny image dithering CLI

A small command‑line tool to dither PNG images using several classic algorithms and palettes.

Requirements
- Ruby 2.6+ (or newer)
- chunky_png gem: gem install chunky_png

Quick start
1) Install dependency: gem install chunky_png
2) Run the CLI:
   ruby main.rb input.png output.png [options]

Common options
- --palette NAME
  Built‑ins: bilevel (default), gray4, gray8, gray16, gameboy, pico8, solar8, rainbow, warm6, cool6, mono_red4, mono_green4, mono_blue4, vibrant8, pastel8
- --palette COLORS
  Custom comma‑separated hex colors, e.g.: "#000,#777,#fff"
- --method NAME
  Dithering methods: floyd (default), threshold, atkinson, jjn, stucki, burkes, sierra, sierra2, sierra_lite, stevenson, bayer2, bayer4, bayer8, cluster4, random
- --gamma G
  Gamma for luminance calculations (default: 2.2)
- --help
  Show built‑in help

Examples
- Simple black/white Floyd–Steinberg:
  ruby main.rb photo.png out.png

- 4‑level grayscale with Atkinson:
  ruby main.rb photo.png out.png --palette gray4 --method atkinson

- Custom tri‑tone palette (dark gray, mid gray, white) with threshold:
  ruby main.rb photo.png out.png --palette "#222,#777,#fff" --method threshold

Notes
- Input and output are PNG files.
- If you see an error about missing chunky_png, install it with: gem install chunky_png
- To see all options any time: ruby main.rb --help
