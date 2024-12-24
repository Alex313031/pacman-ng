# Emscripten

## Build

```
./autogen.sh
emconfigure ./configure 'CXXFLAGS=-O3 -flto -fno-rtti -fno-exceptions'
emmake make
```

## Link

```
em++ -O3 -flto -fno-rtti -fno-exceptions src/*.o -o index.html -sUSE_SDL=2 -sUSE_SDL_IMAGE=2 -sSDL2_IMAGE_FORMATS=png -sUSE_SDL_MIXER=2 -sSDL2_MIXER_FORMATS=wav -sUSE_SDL_TTF=2 -sASYNCIFY -sASYNCIFY_IGNORE_INDIRECT -sASYNCIFY_ONLY=@funcs.txt -sENVIRONMENT=web --preload-file data/fonts/@fonts/ --preload-file data/gfx/@gfx/ --preload-file data/sounds/@sounds/ --preload-file data/txt/@txt/ --closure 1 -sEXPORTED_RUNTIME_METHODS=['allocate']
```
