# cub3D

A simple Wolfenstein-3D style raycaster written in C using MiniLibX.

## Features

- Parse and validate `.cub` scene files
- Load wall textures from XPM files (`NO`, `SO`, `WE`, `EA`)
- Floor and ceiling colors (`F`, `C`)
- Real-time 3D rendering with DDA raycasting
- Player movement and camera rotation

## Project Structure

- `src/` core parsing, validation, and game logic
- `src/render/` rendering, movement, input, textures, and MLX lifecycle
- `lib/libft/` custom C utility library
- `lib/ft_printf/` printf implementation
- `mlx/` macOS MiniLibX
- `mlx_linux/` Linux MiniLibX
- `test_map/` example `.cub` map(s)

## Build

From the project root:

```bash
make
```

This builds:

- `libft`
- `ft_printf`
- `mlx` (macOS) or `mlx_linux` (Linux)
- final executable: `cub3D`

Useful targets:

```bash
make clean
make fclean
make re
```

## Run

```bash
./cub3D path/to/map.cub
```

Example:

```bash
./cub3D test_map/test_map.cub
```

## Controls

- `W` move forward
- `S` move backward
- `A` strafe left
- `D` strafe right
- `Left Arrow` rotate left
- `Right Arrow` rotate right
- `ESC` quit

## `.cub` File Format

Your scene file must include:

1. Texture paths:
   - `NO path/to/north_texture.xpm`
   - `SO path/to/south_texture.xpm`
   - `WE path/to/west_texture.xpm`
   - `EA path/to/east_texture.xpm`
2. Colors:
   - `F R,G,B` (floor)
   - `C R,G,B` (ceiling)
3. Map grid made from:
   - `1` wall
   - `0` empty walkable space
   - player start: one of `N`, `S`, `E`, `W`

Notes:

- The input filename must end with `.cub`
- Texture files must be valid `.xpm`
- Map must be valid/closed according to parser checks

## Requirements

- C compiler (`cc`)
- `make`
- Standard C math/system libs
- MiniLibX dependencies (platform-specific)

## Common Issues

- **Wrong argument count**: run with exactly one `.cub` file
- **Incorrect file extension**: file must end in `.cub`
- **Texture file is invalid**: verify each texture path and `.xpm` content
- **Map parsing error**: ensure scene elements and map format are valid


