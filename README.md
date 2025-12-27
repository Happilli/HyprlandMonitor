To use, first build:
```
cmake  -DCMAKE_INSTALL_PREFIX=$HOME/.local/lib/qt6/qml 
make
cmake --install .
```
Update the shell:
```
export LD_LIBRARY_PATH="$HOME/.local/lib/qt6/qml:$LD_LIBRARY_PATH"
export QML2_IMPORT_PATH="$HOME/.local/lib/qt6/qml:$QML2_IMPORT_PATH"
```

[check the Implementation](https://github.com/RyuZinOh/.dotfiles/blob/main/quickshell/Services/Overview/HyprlandData.qml)
