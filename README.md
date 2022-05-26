edcltool - инструмент для написания edcl сценариев на языке lua.
Этот файл содержит краткую инструкцию по его сборке и применению


# Linux

Для сборки, убедитесь, что в системе есть необходимые зависимости.

lua версии 5.2 или позднее, с заголовочными файлами, пакеты:
liblua5.20 и liblua5.2-dev (Для debian/ubuntu)

```
sudo apt install lua5.2
sudo apt install liblua5.2-dev
sudo apt install liblua5.2-0
```
Распакуйте дерево исходных кодов.

tar vxf edcltool.tar.gz

Произведите сблрку и установку в систему
средствами cmake

```
cd edcltool
mkdir build
cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr
make
sudo make install
```
Так же можно собрать debian пакет, выполнив команду

dpkg-buildpackage

В директории с исходными кодами edcltool

в каталоге examples есть примеры сценариев. Для запуска сценариев используйте
команду edcltool -f имя_файла_сценария
команда -h выведет справку по дополнительным флагам.


#Windows

- Необходимо установить cmake и mingw32. 64-битные сборки не поддерживаются!
- Убедиться, что в PATH есть sh.exe из идущего вместе с MinGW msys
- Если для доступа к интернету необходим прокси, то настроить установить переменные окружения
HTTP_PROXY/HTTPS/PROXY.

```
mkdir build
cd build
cmake .. -G "MSYS Makefiles" -DEDCL_PORTABLE=Yes
make
make package
```
Будет создан zip файл с дистрибутивом программы.

Опциональный флаг -DEDCL_PORTABLE=Yes включает портативную сборку:
edcltool.exe будет искать lua библиотеки в каталоге, где был запущен.
