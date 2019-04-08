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
git clone https://github.com/msoos/cryptominisat.git
cd cryptominisat
git submodule update --init

cd utils
git clone https://github.com/msoos/cryptominisat_web
cd ..

mkdir build & cd build
ln -s ../utils/build_scripts/*.sh .
./build_emscripten.sh
cp *.wasm *.js ../utils/cryptominisat_web

cd ../utils/cryptominisat_web
git add *
git commit -a
```

You also need emscripten installed and the installation SDK has to be put into the script "build_emscripten.sh"
>>>>>>> Updating the system to the newest version + adding README + smaller demo
