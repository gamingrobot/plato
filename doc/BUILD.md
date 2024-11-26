# Build

Start by cloning the repository:

```sh
git clone https://github.com/baskerville/plato.git
cd plato
```

## Plato

#### Preliminary

Install the appropriate [compiler toolchain](https://releases.linaro.org/components/toolchain/binaries/4.9-2017.01/arm-linux-gnueabihf/) (the binaries of the `bin` directory need to be in your path).

Install the required dependencies: `wget`, `curl`, `git`, `pkg-config`, `unzip`, `jq`, `patchelf`.

Install *[rustup](https://www.rust-lang.org/tools/install)*:
```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Install the appropriate target:
```sh
rustup target add arm-unknown-linux-gnueabihf
```

### Build Phase

```sh
./build.sh
```

### Distribution

```sh
./dist.sh
```

## Developer Tools

Install the required dependencies: *DjVuLibre*, *FreeType*, *HarfBuzz*.

```
djvulibre-devel freetype-devel harfbuzz-devel gumbo-parser-devel openjpeg2-devel jbig2dec-devel
```

MuPDF 1.23.11 needs to be exact version (build from source)

```
make HAVE_X11=no HAVE_GLUT=no shared
cp thirdparty/mupdf/build/shared-release/libmupdf.so target/debug/
```

### Emulator

Install one additional dependency: *SDL2*.

You can then run the emulator with:
```sh
./run-emulator.sh
```

### Importer

You can install the importer with:
```sh
./install-importer.sh
```
