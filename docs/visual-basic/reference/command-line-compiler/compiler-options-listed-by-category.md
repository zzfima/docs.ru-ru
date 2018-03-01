---
title: "Параметры компилятора Visual Basic по категориям"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e4ba86f15e51fdceb09c7e005e2af4fa0f9f592f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Параметры компилятора Visual Basic по категориям
Компилятор командной строки [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] служит альтернативой программам компиляции в составе интегрированной среды разработки [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. Ниже приведен список параметров компилятора командной строки [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], отсортированных по функциональной категории.  
  
## <a name="compiler-output"></a>Сообщения компилятора  
  
|Параметр|Цель|  
|---|---|  
|[/nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Подавляет сведения баннера компилятора.|  
|[/utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Отображает выходные данные компилятора в кодировке UTF-8.|  
|[/verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Отображает дополнительные сведения во время компиляции.|  
|`/modulename:<string>`|Укажите имя исходного модуля.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Укажите язык для выходных данных компилятора.|  
  
## <a name="optimization"></a>Оптимизация  
  
|Параметр|Цель|  
|---|---|  
|[/filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Задает выравнивание размеров выходного файла.|  
|[/optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Включает или отключает оптимизацию.|  
  
## <a name="output-files"></a>Выходные файлы  
  
|Параметр|Назначение|  
|---|---|  
|[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Сведение документирующих комментариев в XML-файл.|  
|[/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Задает для компилятора целевой объект [!INCLUDE[Compact](~/includes/compact-md.md)].|  
|[/out](../../../visual-basic/reference/command-line-compiler/out.md)|Задает выходной файл.|  
|[/target](../../../visual-basic/reference/command-line-compiler/target.md)|Задает формат выходного файла.|  
  
## <a name="net-assemblies"></a>Сборки .NET  
  
|Параметр|Цель|  
|---|---|  
|[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.|  
|[/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Указывает, будет ли сборка полностью или частично подписана.|  
|[/imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Импортирует пространство имен из указанной сборки.|  
|[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.|  
|[/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.|  
|[/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Указывает расположение ссылок на сборки с [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.|  
|[/reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Импортирует метаданные из сборки.|  
|[/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Указывает имя сборки, частью которого будет данный модуль.|  
|`/analyzer`|Запускает анализаторы из этой сборки (краткая форма: /a)|  
|`/additionalfile`|Имена дополнительных файлов, которые непосредственно не влияют на создание кода, но могут использоваться анализаторами для выдачи ошибок или предупреждений.|  
  
## <a name="debuggingerror-checking"></a>Отладка и проверка на ошибки  
  
|Параметр|Цель|  
|---|---|  
|[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Создает файл, содержащий сведения, позволяющие легко создать отчет об ошибке.|  
|[/debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Создает отладочную информацию.|  
|[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Отключает возможность компилятора создавать предупреждения.|  
|[/quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Запрещает компилятору показывать код синтаксических ошибок и предупреждений.|  
|[/removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Отключает проверку переполнения для целочисленных значений.|  
|[/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Приравнивает предупреждения к ошибкам.|  
|`/ruleset:<file>`|Укажите файл набора правил, который отключает определенные диагностики.|  
  
## <a name="help"></a>Справка  
  
|Параметр|Цель|  
|---|---|  
|[/?](../../../visual-basic/reference/command-line-compiler/help.md)|Отображает параметры компилятора. Эта команда аналогична параметру `/help`. Компиляция не происходит.|  
|[/help](../../../visual-basic/reference/command-line-compiler/help.md)|Отображает параметры компилятора. Эта команда аналогична параметру `/?`. Компиляция не происходит.|  
  
## <a name="language"></a>Язык  
  
|Параметр|Цель|  
|---|---|  
|[/langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Укажите версию языка: 9 &#124; 9.0 &#124; 10 &#124; 10.0 &#124; 11 &#124; 11.0.|  
|[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Принудительное явное объявление переменных.|  
|[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Принудительное применение строгой семантики.|  
|[/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Указывает, будут ли сравнения строк двоичными или следует использовать семантику языкового стандарта.|  
|[/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Включает использование локального определения типов в различных объявлениях.|  
  
## <a name="preprocessor"></a>Препроцессор  
  
|Параметр|Цель|  
|---|---|  
|[/define](../../../visual-basic/reference/command-line-compiler/define.md)|Определяет символы условной компиляции.|  
  
## <a name="resources"></a>Ресурсы  
  
|Параметр|Цель|  
|---|---|  
|[/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Создает ссылку на управляемый ресурс.|  
|[/resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Внедряет управляемый ресурс в сборку.|  
|[/win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Внедряет ICO-файл в выходной файл.|  
|[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Внедряет ресурс Win32 в выходной файл.|  
  
## <a name="miscellaneous"></a>Прочее  
  
|Параметр|Цель|  
|---|---|  
|[@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Указывает файл ответа.|  
|[/baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Задает базовый адрес библиотеки DLL.|  
|[/codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Задает кодовую страницу, которая будет использоваться для всех файлов исходного кода при компиляции.|  
|[/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Указывает, как компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должен сообщать о внутренних ошибках.|  
|[/highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Сообщает ядру Windows, поддерживает ли указанный исполняемый файл технологию Address Space Layout Randomization (ASLR) с высокой энтропией.|  
|[/main](../../../visual-basic/reference/command-line-compiler/main.md)|Указывает класс, который содержит `Sub``Main` процедуры при запуске.|  
|[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|Не компилировать с Vbc.rsp.|  
|[/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Указывает компилятору не ссылаться на стандартные библиотеки.|  
|[/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Указывает компилятору не внедрять манифест приложения в исполняемый файл.|  
|[/platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Указывает компилятору платформу процессора для выходного файла.|  
|[/recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Выполняет поиск в подкаталогах исходных файлов для компиляции.|  
|[/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Задает пространство имен для всех объявлений типов.|  
|[/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Задает расположение библиотек mscorlib.dll и microsoft.visualbasic.dll.|  
|[/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.|  
|[/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).|  
|`/parallel[+&#124;-]`|Указывает, следует ли использовать параллельную сборку (+).|  
|`/checksumalgorithm:<alg>`|Указывает алгоритм для расчета контрольной суммы файла источника, хранящегося в PDB.  Поддерживаемые значения: SHA1 (по умолчанию) или SHA256.|  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора Visual Basic в алфавитном порядке](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md)  
 [Знакомство с конструктором проектов](http://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7)  
 [Параметры компилятора C# в алфавитном порядке](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [Параметры компилятора C#, упорядоченные по категориям](../../../csharp/language-reference/compiler-options/listed-by-category.md)
