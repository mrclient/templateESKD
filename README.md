## Общая информация
Репозиторий содержит шаблон для текстовых отчетов, в которых требуется наличие ГОСТ-овских рамок.
Шаблон основан на пакете [eskdx](https://ctan.org/pkg/eskdx).

## Пример оформления
Доступен в поддиректории build.

## Пример команд для сборки файла в Ubuntu Linux
* для файла, не содержащего ссылок на источники:

    Несколько раз выполнить

    ```
    $ pdflatex -output-directory=build main.tex
    ```

* для файла, содержащего ссылки на источники:

    Выполнить однократно следующие команды:

    ```
    $ pdflatex -output-directory=build main.tex
    $ bibtex build/main.aux
    ```

    а затем завершить сборку, несколько раз дав команду

    ```
    $ pdflatex -output-directory=build main.tex
    ```

## Возможные решения ожидаемых проблем
### После сборки скачанных исходников в документе пропадает графа 26
Попробуйте внести изменения, представленные в файле patches/eskdstamp.patch, в файл eskdstamp.sty пакета eskdx на своем компьютере.
На Ubuntu Linux это можно сделать, например, с помощью следующих команд:
```bash
$ cd /usr/share/texlive/texmf-dist/tex/latex/eskdx
$ sudo patch < СООТВЕТСТВУЮЩИЙ_ПУТЬ/eskdstamp.patch
```
**Примечания**:
1. Нумерацию граф можно посмотреть в приложении Б [данного документа](http://mirror.macomnet.net/pub/CTAN/macros/latex/contrib/eskdx/manual/eskdx.pdf).
2. Описание формата содержимого файлов \*.patch можно посмотреть, например, [здесь](https://ru.wikipedia.org/wiki/Diff#%D0%A3%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9_%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82).

### Слово "Изм." штампа не влезает в отведенную для него графу
Попробуйте внести изменения, представленные в файле patches/eskdrussian.patch, в файл eskdrussian.def пакета eskdx на своем компьютере.
На Ubuntu Linux это можно сделать, например, с помощью следующих команд:
```bash
$ cd /usr/share/texlive/texmf-dist/tex/latex/eskdx
$ sudo patch < СООТВЕТСТВУЮЩИЙ_ПУТЬ/eskdrussian.patch
```
