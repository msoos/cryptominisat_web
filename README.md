This is an online version of the SAT solver CryptoMiniSat. It has been compiled with emscripten using:

```
cmake -DENABLE_PYTHON_INTERFACE=OFF -DNOM4RI=ON \
    -DENABLE_TESTING=OFF -DNOZLIB=ON -DONLY_SIMPLE=ON \
    -DEMSCIPTEN=ON \
    -DCMAKE_TOOLCHAIN_FILE=/usr/lib/emscripten/cmake/Modules/Platform/Emscripten.cmake \
    ..
make VERBOSE=1 -j4
```

This generates a wasm and js file which then can be used inside the browser.

#How to update this repository

```
git clone https://github.com/msoos/cryptominisat
git submodule update --init

# get this repository
cd utils
git clone git@github.com:msoos/cryptominisat_web.git
cd ..

# build
mkdir build && cd build
./build_emscripten.sh
cp *.wasm *.js ../utils/emscripten/

# test
cd ../utils/emscripten/
docker run -p 80:80 -v $(pwd):/usr/share/nginx/html nginx

# commit
git add *.wasm *.js
git commit -a
```
