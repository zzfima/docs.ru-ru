---
title: "Параметры компилятора C#, упорядоченные по категориям"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 410cad333b023e59d8c093d70d0e248504625dd6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="c-compiler-options-listed-by-category"></a>Параметры компилятора C#, упорядоченные по категориям
Следующие параметры компилятора упорядочены по категории. Алфавитный список см. в разделе [Параметры компилятора C# в алфавитном порядке](../../../csharp/language-reference/compiler-options/listed-alphabetically.md).  
  
### <a name="optimization"></a>Оптимизация  
  
|Параметр|Цель|  
|------------|-------------|  
|[-filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|Задает размер разделов в выходном файле.|  
|[-optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|Включает или отключает оптимизацию.|  
  
### <a name="output-files"></a>Выходные файлы  
  
|Параметр|Цель|  
|------------|-------------|  
|[-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|Задает XML-файл, куда должны записываться обработанные комментарии к документации.|  
|[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|Задает выходной файл.|  
|[/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|Указывает имя и расположение PDB-файла.|  
|[-platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|Укажите выходную платформу.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Укажите язык для выходных данных компилятора.|  
|[/refout](refout-compiler-option.md)|Создание ссылочной сборки в дополнение к основной.|  
|[/refonly](refonly-compiler-option.md)|Создание ссылочной сборки вместо основной.|  
|[-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|Задает формат выходного файла, используя один из пяти параметров: [-target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [-target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) или [-target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md).|  
|-modulename:\<строка>|Укажите имя исходного модуля.|  
  
### <a name="net-framework-assemblies"></a>Сборки .NET Framework  
  
|Параметр|Цель|  
|------------|-------------|  
|[-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|Задает один или несколько модулей, которые должны быть частью этой сборки.|  
|[-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|Указывает компилятору добавить открытый ключ, но оставить сборку без подписи.|  
|[-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|Задает имя контейнера криптографического ключа.|  
|[-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|Задает имя файла, содержащего криптографический ключ.|  
|[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|Задает расположение сборок, указанных с помощью параметра [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).|  
|[-nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|Указывает компилятору не импортировать стандартную библиотеку (mscorlib.dll).|  
|[-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|Импортирует метаданные из файла, содержащего сборку.|  
|-analyzer|Запускает анализаторы из этой сборки (краткая форма: /a)|  
|-additionalfile|Имена дополнительных файлов, которые непосредственно не влияют на создание кода, но могут использоваться анализаторами для выдачи ошибок или предупреждений.|  
  
### <a name="debuggingerror-checking"></a>Отладка и проверка на ошибки  
  
|Параметр|Цель|  
|------------|-------------|  
|[-bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|Создает файл, содержащий сведения, позволяющие легко создать отчет об ошибке.|  
|[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|Указывает, будут ли целочисленные арифметические операции, переполняющие границы типа данных, вызывать исключение во время выполнения.|  
|[-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|Указывает компилятору выдавать отладочные сведения.|  
|[-errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|Устанавливает поведение отчетов об ошибках.|  
|[/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|Задает абсолютный путь к файлу в выходных данных компилятора.|  
|[-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|Подавляет создание компилятором указанных предупреждений.|  
|[/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|Устанавливает уровень предупреждений.|  
|[-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|Приравнивает предупреждения к ошибкам.|  
|-ruleset:\<файл>|Укажите файл набора правил, который отключает определенные диагностики.|  
  
### <a name="preprocessor"></a>Препроцессор  
  
|Параметр|Цель|  
|------------|-------------|  
|[-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|Определяет символы препроцессора.|  
  
### <a name="resources"></a>Ресурсы  
  
|Параметр|Цель|  
|------------|-------------|  
|[-link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|Делает сведения о типах COM в указанных сборках доступными для проекта.|  
|[-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|Создает ссылку на управляемый ресурс.|  
|[-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|Внедряет ресурс .NET Framework в выходной файл.|  
|[-win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|Указывает ICO-файл для вставки в выходной файл.|  
|[/win32res:](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|Задает ресурс Win32 для вставки в выходной файл.|  
  
### <a name="miscellaneous"></a>Прочее  
  
|Параметр|Цель|  
|------------|-------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|Указывает файл ответа.|  
|[-?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Перечисляет параметры компилятора в stdout.|  
|[-baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|Указывает предпочтительный базовый адрес для загрузки DLL.|  
|[-codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|Задает кодовую страницу, которая будет использоваться для всех файлов исходного кода при компиляции.|  
|[-help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Перечисляет параметры компилятора в stdout.|  
|[-highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|Указывает, что исполняемый файл поддерживает технологию Address Space Layout Randomization (ASLR).|  
|[-langversion](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|Укажите режим языковой версии: Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1 или Latest |  
|[-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|Указывает местоположение метода **Main**.|  
|[-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|Предписывает компилятору не компилировать csc.rsp.|  
|[-nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|Подавляет сведения баннера компилятора.|  
|[-recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|Выполняет поиск в подкаталогах исходных файлов для компиляции.|  
|[-subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|Задает минимальную версию подсистемы, которую может использовать исполняемый файл.|  
|[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|Разрешает компиляцию кода, использующего ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md).|  
|[-utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|Отображает выходные данные компилятора в кодировке UTF-8.|  
|-parallel[+&#124;-]|Указывает, следует ли использовать параллельную сборку (+).|  
|-checksumalgorithm:\<алгоритм>|Указывает алгоритм для расчета контрольной суммы файла источника, хранящегося в PDB.  Поддерживаемые значения: SHA1 (по умолчанию) или SHA256.|  
  
## <a name="obsolete-options"></a>Устаревшие параметры  
  
|Параметр|Цель|  
|---|---|  
|-incremental|Включает инкрементную компиляцию.|  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Параметры компилятора C# в алфавитном порядке](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
