---
title: Параметры компилятора C# в алфавитном порядке
ms.date: 05/15/2018
helpviewer_keywords:
- compiler options [C#], listed alphabetically
- C# language, compiler options listed alphabetically
- Visual C# compiler, options listed alphabetically
- Visual C#, compiler options listed alphabetically
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
ms.openlocfilehash: d6d471cd27f35de6325a130e6c909d13cb1dcc85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972743"
---
# <a name="c-compiler-options-listed-alphabetically"></a>Параметры компилятора C# в алфавитном порядке

Следующие параметры компилятора приведены в алфавитном порядке. Список параметров по категориям см. в разделе [Параметры компилятора C#, упорядоченные по категориям](listed-by-category.md).

|Параметр|Цель|
|------------|-------------|
|[@](response-file-compiler-option.md)|Считывает файл ответов с дополнительными параметрами.|
|[-?](help-compiler-option.md)|Отображает сообщение об использовании в stdout.|
|-additionalfile|Имена дополнительных файлов, которые непосредственно не влияют на создание кода, но могут использоваться анализаторами для выдачи ошибок или предупреждений.|
|[-addmodule](addmodule-compiler-option.md)|Включает указанные модули в эту сборку.|
|-analyzer|Запускает анализаторы из этой сборки (краткая форма: -a)|
|[/appconfig](appconfig-compiler-option.md)|Указывает расположение файла app.config во время привязки сборки.|
|[-baseaddress](baseaddress-compiler-option.md)|Задает базовый адрес библиотеки для сборки.|
|[-bugreport](bugreport-compiler-option.md)|Создает файл отчета об ошибках. Этот файл будет отправляться вместе со сведениями о сбое, если использовать параметр с -errorreport:prompt или -errorreport:send.|
|[/checked](checked-compiler-option.md)|Указывает компилятору создавать проверки переполнения.|
|-checksumalgorithm:\<алгоритм>|Указывает алгоритм для расчета контрольной суммы исходного файла, хранящегося в PDB.  Допустимые значения: SHA256 (по умолчанию) или SHA1.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256. |
|[-codepage](codepage-compiler-option.md)|Указывает кодовую страницу, используемую при открытии исходных файлов.|
|[-debug](debug-compiler-option.md)|Выдает сведения об отладке.|
|[-define](define-compiler-option.md)|Определяет символы условной компиляции|
|[-delaysign](delaysign-compiler-option.md)|Отложенная подпись сборки с помощью только открытой части ключа строгого имени.|
|[-deterministic](deterministic-compiler-option.md)|Указывает компилятору на необходимость вывода сборки, чье двоичное содержимое идентично в разных компиляциях, если входные данные идентичны.|
|[-doc](doc-compiler-option.md)|Задает создаваемый XML-файл документации.|
|-embed|Внедрение всех исходных файлов в PDB-файл.|
|-embed:\<список_файлов>|Внедрение определенных файлов в PDB-файл.|
|-errorendlocation|Выходные строка и столбец конечного расположения каждой ошибки.|
|-errorlog:\<файл>|Укажите файл для записи данных диагностики компилятора и анализатора в журнал.|
|[-errorreport](errorreport-compiler-option.md)|Указывает способ обработки внутренних ошибок компилятора: prompt, send или none. Значение по умолчанию — none.|
|[-filealign](filealign-compiler-option.md)|Указывает выравнивание для разделов выходного файла.|
|[/fullpaths](fullpaths-compiler-option.md)|Указывает компилятору создавать полные пути.|
|[-help](help-compiler-option.md)|Отображает сообщение об использовании в stdout.|
|[-highentropyva](highentropyva-compiler-option.md)|Указывает, что поддерживается технология ASLR с высокой энтропией.|
|-incremental|Включает инкрементную компиляцию [устарело].|
|[-keycontainer](keycontainer-compiler-option.md)|Задает контейнер ключа для строгого имени.|
|[-keyfile](keyfile-compiler-option.md)|Задает файл ключа для строгого имени.|
|[-langversion:\<строка>](langversion-compiler-option.md)|Укажите версию языка: по умолчанию, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 или последняя версия |
|[/lib](lib-compiler-option.md)|Задает дополнительные каталоги для поиска ссылок.|
|[-link](link-compiler-option.md)|Делает сведения о типах COM в указанных сборках доступными для проекта.|
|[-linkresource](linkresource-compiler-option.md)|Включает указанные файлы ресурсов в эту сборку.|
|[-main](main-compiler-option.md)|Задает тип, содержащий точку входа (все другие возможные точки входа игнорируются).|
|[-moduleassemblyname](moduleassemblyname-compiler-option.md)|Указывает сборку, к неоткрытым типам которой может обращаться .netmodule.|
|-modulename:\<строка>|Укажите имя исходного модуля.|
|[-noconfig](noconfig-compiler-option.md)|Указывает, что компилятор не должен автоматически включать файл CSC.RSP.|
|[-nologo](nologo-compiler-option.md)|Запрещает отображение сообщения компилятора об авторских правах.|
|[-nostdlib](nostdlib-compiler-option.md)|Указывает компилятору не ссылаться на стандартную библиотеку (mscorlib.dll).|
|[-nowarn](nowarn-compiler-option.md)|Отключает определенные предупреждающие сообщения.|
|[-nowin32manifest](nowin32manifest-compiler-option.md)|Указывает компилятору не внедрять манифест приложения в исполняемый файл.|
|[-optimize](optimize-compiler-option.md)|Включает или отключает оптимизацию.|
|[-out](out-compiler-option.md)|Задает имя выходного файла (по умолчанию это базовое имя файла с классом main или имя первого файла).|
|-parallel[+&#124;-]|Указывает, следует ли использовать параллельную сборку (+).|
|[-pathmap](pathmap-compiler-option.md)|Указание сопоставления для вывода компилятором имен исходных путей.|
|[/pdb](pdb-compiler-option.md)|Указывает имя и расположение PDB-файла.|
|[-platform](platform-compiler-option.md)|Ограничивает платформу выполнения кода: x86, Itanium, x64, anycpu или anycpu32bitpreferred. Значение по умолчанию — anycpu.|
|[/preferreduilang](preferreduilang-compiler-option.md)|Задает язык, используемый для вывода компилятора.|
|[-publicsign](publicsign-compiler-option.md)|Применение открытого ключа без подписи сборки. При этом в сборке устанавливается бит, указывающий на то, что она подписана.|
|[-recurse](recurse-compiler-option.md)|Включает все файлы в текущем каталоге и подкаталогах в соответствии с заданным шаблоном.|
|[-reference](reference-compiler-option.md)|Ссылается на метаданные из указанных файлов сборки.|
|[/refout](refout-compiler-option.md)|Создание ссылочной сборки в дополнение к основной.|
|[/refonly](refonly-compiler-option.md)|Создание ссылочной сборки вместо основной.|
|-reportanalyzer|Включение в отчет дополнительных сведений об анализаторе, включая время выполнения.|
|[-resource](resource-compiler-option.md)|Внедряет указанный ресурс.|
|-ruleset:\<файл>|Укажите файл набора правил, который отключает определенные диагностики.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Задает минимальную версию подсистемы, которую может использовать исполняемый файл.|
|[-target](target-compiler-option.md)|Задает формат выходного файла, используя один из четырех параметров: [-target:appcontainerexe](target-appcontainerexe-compiler-option.md), [-target:exe](target-exe-compiler-option.md), [-target:library](target-library-compiler-option.md), [-target:module](target-module-compiler-option.md), [-target:winexe](target-winexe-compiler-option.md), [-target:winmdobj](target-winmdobj-compiler-option.md).|
|[/unsafe](unsafe-compiler-option.md)|Разрешает небезопасный ([unsafe](../keywords/unsafe.md)) код.|
|[-utf8output](utf8output-compiler-option.md)|Выводит сообщения компилятора в кодировке UTF-8.|
|-version|Отображение номера версии компилятора и выход.|
|[/warn](warn-compiler-option.md)|Устанавливает уровень предупреждений (0–4).|
|[-warnaserror](warnaserror-compiler-option.md)|Задает интерпретацию определенных предупреждений как ошибок.|
|[-win32icon](win32icon-compiler-option.md)|Задает использование этого значка для вывода.|
|[-win32manifest](win32manifest-compiler-option.md)|Задает пользовательский файл манифеста win32.|
|[/win32res:](win32res-compiler-option.md)|Задает файл ресурсов win32 (RES-файл).|

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](index.md)
- [Параметры компилятора C#, упорядоченные по категориям](listed-by-category.md)
- [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [Элемент \<compiler>](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)
