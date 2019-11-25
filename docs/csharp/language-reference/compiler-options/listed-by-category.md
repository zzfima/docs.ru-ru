---
title: Параметры компилятора C#, упорядоченные по категориям
ms.date: 05/15/2018
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
ms.openlocfilehash: 5cd5607c25dabd8f56ebb58366116666e8e649ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972704"
---
# <a name="c-compiler-options-listed-by-category"></a>Параметры компилятора C#, упорядоченные по категориям

Следующие параметры компилятора упорядочены по категории. Алфавитный список см. в разделе [Параметры компилятора C# в алфавитном порядке](listed-alphabetically.md).

## <a name="optimization"></a>Оптимизация

|Параметр|Цель|
|------------|-------------|
|[-filealign](filealign-compiler-option.md)|Задает размер разделов в выходном файле.|
|[-optimize](optimize-compiler-option.md)|Включает или отключает оптимизацию.|

## <a name="output-files"></a>Выходные файлы

|Параметр|Цель|
|------------|-------------|
|[-deterministic](deterministic-compiler-option.md)|Указывает компилятору на необходимость вывода сборки, чье двоичное содержимое идентично в разных компиляциях, если входные данные идентичны.|
|[-doc](doc-compiler-option.md)|Задает XML-файл, куда должны записываться обработанные комментарии к документации.|
|[-out](out-compiler-option.md)|Задает выходной файл.|
|[-pathmap](pathmap-compiler-option.md)|Указание сопоставления для вывода компилятором имен исходных путей.|
|[/pdb](pdb-compiler-option.md)|Указывает имя и расположение PDB-файла.|
|[-platform](platform-compiler-option.md)|Укажите выходную платформу.|
|[/preferreduilang](preferreduilang-compiler-option.md)|Укажите язык для выходных данных компилятора.|
|[/refout](refout-compiler-option.md)|Создание ссылочной сборки в дополнение к основной.|
|[/refonly](refonly-compiler-option.md)|Создание ссылочной сборки вместо основной.|
|[-target](target-compiler-option.md)|Задает формат выходного файла, используя один из пяти параметров: [-target:appcontainerexe](target-appcontainerexe-compiler-option.md), [-target:exe](target-exe-compiler-option.md), [-target:library](target-library-compiler-option.md), [-target:module](target-module-compiler-option.md), [-target:winexe](target-winexe-compiler-option.md) или [-target:winmdobj](target-winmdobj-compiler-option.md).|
|-modulename:\<строка>|Укажите имя исходного модуля.|

## <a name="net-framework-assemblies"></a>Сборки .NET Framework

|Параметр|Цель|
|------------|-------------|
|[-addmodule](addmodule-compiler-option.md)|Задает один или несколько модулей, которые должны быть частью этой сборки.|
|[-delaysign](delaysign-compiler-option.md)|Указывает компилятору добавить открытый ключ, но оставить сборку без подписи.|
|[-keycontainer](keycontainer-compiler-option.md)|Задает имя контейнера криптографического ключа.|
|[-keyfile](keyfile-compiler-option.md)|Задает имя файла, содержащего криптографический ключ.|
|[/lib](lib-compiler-option.md)|Задает расположение сборок, указанных с помощью параметра [-reference](reference-compiler-option.md).|
|[-nostdlib](nostdlib-compiler-option.md)|Указывает компилятору не импортировать стандартную библиотеку (mscorlib.dll).|
|[-publicsign](publicsign-compiler-option.md)|Применение открытого ключа без подписи сборки. При этом в сборке устанавливается бит, указывающий на то, что она подписана.|
|[-reference](reference-compiler-option.md)|Импортирует метаданные из файла, содержащего сборку.|
|-analyzer|Запускает анализаторы из этой сборки (краткая форма: /a)|
|-additionalfile|Имена дополнительных файлов, которые непосредственно не влияют на создание кода, но могут использоваться анализаторами для выдачи ошибок или предупреждений.|
|-embed|Внедрение всех исходных файлов в PDB-файл.|
|-embed:\<список_файлов>|Внедрение определенных файлов в PDB-файл.|
## <a name="debuggingerror-checking"></a>Отладка и проверка на ошибки

|Параметр|Цель|
|------------|-------------|
|[-bugreport](bugreport-compiler-option.md)|Создает файл, содержащий сведения, позволяющие легко создать отчет об ошибке.|
|[/checked](checked-compiler-option.md)|Указывает, будут ли целочисленные арифметические операции, переполняющие границы типа данных, вызывать исключение во время выполнения.|
|[-debug](debug-compiler-option.md)|Указывает компилятору выдавать отладочные сведения.|
|[-errorreport](errorreport-compiler-option.md)|Устанавливает поведение отчетов об ошибках.|
|[/fullpaths](fullpaths-compiler-option.md)|Задает абсолютный путь к файлу в выходных данных компилятора.|
|[-nowarn](nowarn-compiler-option.md)|Подавляет создание компилятором указанных предупреждений.|
|[/warn](warn-compiler-option.md)|Устанавливает уровень предупреждений.|
|[-warnaserror](warnaserror-compiler-option.md)|Приравнивает предупреждения к ошибкам.|
|-ruleset:\<файл>|Укажите файл набора правил, который отключает определенные диагностики.|

## <a name="preprocessor"></a>Препроцессор

|Параметр|Цель|
|------------|-------------|
|[-define](define-compiler-option.md)|Определяет символы препроцессора.|

## <a name="resources"></a>Ресурсы

|Параметр|Цель|
|------------|-------------|
|[-link](link-compiler-option.md)|Делает сведения о типах COM в указанных сборках доступными для проекта.|
|[-linkresource](linkresource-compiler-option.md)|Создает ссылку на управляемый ресурс.|
|[-resource](resource-compiler-option.md)|Внедряет ресурс .NET Framework в выходной файл.|
|[-win32icon](win32icon-compiler-option.md)|Указывает ICO-файл для вставки в выходной файл.|
|[/win32res:](win32res-compiler-option.md)|Задает ресурс Win32 для вставки в выходной файл.|

## <a name="miscellaneous"></a>Прочее

|Параметр|Цель|
|------------|-------------|
|[@](response-file-compiler-option.md)|Указывает файл ответа.|
|[-?](help-compiler-option.md)|Перечисляет параметры компилятора в stdout.|
|[-baseaddress](baseaddress-compiler-option.md)|Указывает предпочтительный базовый адрес для загрузки DLL.|
|[-codepage](codepage-compiler-option.md)|Задает кодовую страницу, которая будет использоваться для всех файлов исходного кода при компиляции.|
|[-help](help-compiler-option.md)|Перечисляет параметры компилятора в stdout.|
|[-highentropyva](highentropyva-compiler-option.md)|Указывает, что исполняемый файл поддерживает технологию Address Space Layout Randomization (ASLR).|
|[-langversion](langversion-compiler-option.md)|Укажите версию языка: по умолчанию, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 или последняя версия |
|[-main](main-compiler-option.md)|Указывает местоположение метода **Main**.|
|[-noconfig](noconfig-compiler-option.md)|Предписывает компилятору не компилировать csc.rsp.|
|[-nologo](nologo-compiler-option.md)|Подавляет сведения баннера компилятора.|
|[-recurse](recurse-compiler-option.md)|Выполняет поиск в подкаталогах исходных файлов для компиляции.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Задает минимальную версию подсистемы, которую может использовать исполняемый файл.|
|[/unsafe](unsafe-compiler-option.md)|Разрешает компиляцию кода, использующего ключевое слово [unsafe](../keywords/unsafe.md).|
|[-utf8output](utf8output-compiler-option.md)|Отображает выходные данные компилятора в кодировке UTF-8.|
|-parallel[+&#124;-]|Указывает, следует ли использовать параллельную сборку (+).|
|-checksumalgorithm:\<алгоритм>|Указывает алгоритм для расчета контрольной суммы файла источника, хранящегося в PDB.  Допустимые значения: SHA1 (по умолчанию) или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|

## <a name="obsolete-options"></a>Устаревшие параметры

|Параметр|Цель|
|---|---|
|-incremental|Включает инкрементную компиляцию.|

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](index.md)
- [Параметры компилятора C# в алфавитном порядке](listed-alphabetically.md)
- [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
