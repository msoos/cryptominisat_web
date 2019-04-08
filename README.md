This is an online version of the SAT solver CryptoMiniSat. It has been compiled with emscripten using:

```
cmake -DENABLE_PYTHON_INTERFACE=OFF -DNOM4RI=ON \
    -DENABLE_TESTING=OFF -DNOZLIB=ON -DONLY_SIMPLE=ON \
    -DEMSCIPTEN=ON \
    -DCMAKE_TOOLCHAIN_FILE=/zzz/emsdk/emscripten/1.38.0/cmake/Modules/Platform/Emscripten.cmake \
    ..
make VERBOSE=1 -j4
```

This generates a wasm and js file which then can be used inside the browser.
