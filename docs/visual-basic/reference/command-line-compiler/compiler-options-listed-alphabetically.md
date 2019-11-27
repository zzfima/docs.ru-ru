---
title: Параметры компилятора в алфавитном порядке
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
ms.openlocfilehash: c529c03fd3856bbd3d3b26371415907c94ca8d30
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343518"
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Visual Basic параметров компилятора в алфавитном порядке
Компилятор командной строки Visual Basic предоставляется в качестве альтернативы компиляции программ из интегрированной среды разработки Visual Studio (IDE). Ниже приведен список параметров компилятора командной строки Visual Basic отсортированных в алфавитном порядке.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
|Параметр|Цель|  
|------------|-------------|  
|[@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Указывает файл ответа.|  
|[-?](../../../visual-basic/reference/command-line-compiler/help.md)|Отображает параметры компилятора. Эта команда аналогична параметру `-help`. Компиляция не происходит.|  
|`-additionalfile`|Имена дополнительных файлов, которые непосредственно не влияют на создание кода, но могут использоваться анализаторами для выдачи ошибок или предупреждений.|  
|[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.|  
|`-analyzer`|Запускает анализаторы из этой сборки (краткая форма: -a)|  
|[-baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Задает базовый адрес библиотеки DLL.|  
|[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Создает файл, содержащий сведения, позволяющие легко создать отчет об ошибке.|  
|`-checksumalgorithm:<alg>`|Указывает алгоритм для расчета контрольной суммы файла источника, хранящегося в PDB.  Поддерживаемые значения: SHA1 (по умолчанию) или SHA256. <br>Из-за проблем с алгоритмом SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.|  
|[-codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Задает кодовую страницу, которая будет использоваться для всех файлов исходного кода при компиляции.|  
|[-debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Создает отладочную информацию.|  
|[-define](../../../visual-basic/reference/command-line-compiler/define.md)|Определяет символы условной компиляции.|  
|[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Указывает, будет ли сборка полностью или частично подписана.|  
|[-deterministic](../../../visual-basic/reference/command-line-compiler/deterministic.md)|Указывает компилятору на необходимость вывода сборки, чье двоичное содержимое идентично в разных компиляциях, если входные данные идентичны.|
|[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Обрабатывает комментарии к документации в XML-файл.|  
|[-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Указывает, каким образом компилятор Visual Basic должен сообщать о внутренних ошибках компилятора.|  
|[-filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Задает выравнивание размеров выходного файла.|  
|[-help](../../../visual-basic/reference/command-line-compiler/help.md)|Отображает параметры компилятора. Эта команда аналогична параметру `-?`. Компиляция не происходит.|  
|[-highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Определяет, поддерживает ли указанный исполняемый файл технологию Address Space Layout Randomization (ASLR) с высокой энтропией.|  
|[-imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Импортирует пространство имен из указанной сборки.|  
|[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.|  
|[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.|  
|[-langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Укажите версию языка: 9&#124;9,0&#124;10&#124;10,0&#124;11&#124;11,0.|  
|[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Указывает расположение сборок, на которые ссылается параметр [-Reference](../../../visual-basic/reference/command-line-compiler/reference.md) .|  
|[-linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Создает ссылку на управляемый ресурс.|  
|[-main](../../../visual-basic/reference/command-line-compiler/main.md)|Указывает класс, содержащий процедуру `Sub Main`, используемую при запуске.|  
|[-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Указывает имя сборки, частью которого будет данный модуль.|  
|`-modulename:<string>`|Укажите имя исходного модуля.|  
|[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Задает компилятор, предназначенный для .NET Compact Framework.|  
|[-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|Не компилировать с Vbc.rsp.|  
|[-nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Подавляет сведения баннера компилятора.|  
|[-nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Указывает компилятору не ссылаться на стандартные библиотеки.|  
|[-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Отключает возможность компилятора создавать предупреждения.|  
|[-nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Указывает компилятору не внедрять манифест приложения в исполняемый файл.|  
|[-optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Включает или отключает оптимизацию кода.|  
|[-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Указывает, будут ли сравнения строк двоичными или следует использовать семантику языкового стандарта.|  
|[-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Принудительное явное объявление переменных.|  
|[-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Включает использование локального определения типов в различных объявлениях.|  
|[-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Требовать строгой семантики языка.|  
|[-out](../../../visual-basic/reference/command-line-compiler/out.md)|Задает выходной файл.|  
|`-parallel[+&#124;-]`|Указывает, следует ли использовать параллельную сборку (+).|  
|[-platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Указывает компилятору платформу процессора для выходного файла.|  
|`-preferreduilang`|Укажите имя предпочтительного языка вывода.|  
|[-quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Запрещает компилятору показывать код синтаксических ошибок и предупреждений.|  
|[-recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Выполняет поиск в подкаталогах исходных файлов для компиляции.|  
|[-reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Импортирует метаданные из сборки.|  
|[/refonly](refonly-compiler-option.md)|Выводит только ссылочную сборку.|
|[/refout](refout-compiler-option.md)|Указывает выходной путь ссылочной сборки.|
|[-removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Отключает проверку переполнения для целочисленных значений.|  
|[-resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Внедряет управляемый ресурс в сборку.|  
|[-rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Задает пространство имен для всех объявлений типов.|  
|`-ruleset:<file>`|Укажите файл набора правил, который отключает определенные диагностики.|  
|[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Задает расположение библиотек mscorlib.dll и microsoft.visualbasic.dll.|  
|[-subsystemversion](../../../visual-basic/reference/command-line-compiler/subsystemversion.md)|Задает минимальную версию подсистемы, которую может использовать созданный исполняемый файл.|  
|[-target](../../../visual-basic/reference/command-line-compiler/target.md)|Задает формат выходного файла.|  
|[-utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Отображает выходные данные компилятора в кодировке UTF-8.|  
|[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.|  
|[-verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Отображает дополнительные сведения во время компиляции.|  
|[-warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Приравнивает предупреждения к ошибкам.|  
|[-win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Внедряет ICO-файл в выходной файл.|  
|[-win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).|  
|[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Внедряет ресурс Win32 в выходной файл.|  
  
## <a name="see-also"></a>См. также

- [Параметры компилятора Visual Basic по категориям](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-by-category.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
