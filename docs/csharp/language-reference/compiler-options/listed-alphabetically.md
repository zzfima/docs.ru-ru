---
title: "Параметры компилятора C# в алфавитном порядке (C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- compiler options [C#], listed alpabetically
- C# language, compiler options listed alphabitically
- Visual C# compiler, options listed alphabetically
- Visual C#, compiler options listed alphabetically
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
caps.latest.revision: 25
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 91582d214c2f8a72d383a0ac17e409167fda5065
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="c-compiler-options-listed-alphabetically"></a>Параметры компилятора C# в алфавитном порядке
Следующие параметры компилятора приведены в алфавитном порядке. Список параметров по категориям см. в разделе [Параметры компилятора C#, упорядоченные по категориям](../../../csharp/language-reference/compiler-options/listed-by-category.md).  
  
|Параметр|Назначение|  
|------------|-------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|Считывает файл ответов с дополнительными параметрами.|  
|[/?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Отображает сообщение об использовании в stdout.|  
|`/additionalfile`|Имена дополнительных файлов, которые непосредственно не влияют на создание кода, но могут использоваться анализаторами для выдачи ошибок или предупреждений.|  
|[/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|Включает указанные модули в эту сборку.|  
|`/analyzer`|Запускает анализаторы из этой сборки (краткая форма: /a)|  
|[/appconfig](../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)|Указывает расположение файла app.config во время привязки сборки.|  
|[/baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|Задает базовый адрес библиотеки для сборки.|  
|[/bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|Создает файл отчета об ошибках. Этот файл будет отправляться вместе со сведениями о сбое, если параметр используется с **/errorreport:prompt** или **/errorreport:send**.|  
|[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|Указывает компилятору создавать проверки переполнения.|  
|`/checksumalgorithm:<alg>`|Указывает алгоритм для расчета контрольной суммы файла источника, хранящегося в PDB.  Поддерживаемые значения: SHA1 (по умолчанию) или SHA256.|  
|[/codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|Указывает кодовую страницу, используемую при открытии исходных файлов.|  
|[/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|Выдает сведения об отладке.|  
|[/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|Определяет символы условной компиляции|  
|[/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|Отложенная подпись сборки с помощью только открытой части ключа строгого имени.|  
|[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|Задает создаваемый XML-файл документации.|  
|[/errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|Указывает способ обработки внутренних ошибок компилятора: prompt, send или none. Значение по умолчанию — none.|  
|[/filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|Указывает выравнивание для разделов выходного файла.|  
|[/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|Указывает компилятору создавать полные пути.|  
|[/help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Отображает сообщение об использовании в stdout.|  
|[/highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|Указывает, что поддерживается технология ASLR с высокой энтропией.|  
|**/incremental**|Включает инкрементную компиляцию [устарело].|  
|[/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|Задает контейнер ключа для строгого имени.|  
|[/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|Задает файл ключа для строгого имени.|  
|[/langversion:\<string>](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|Укажите режим языковой версии: ISO-1, ISO-2, 3, 4, 5, 6 или Default|  
|[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|Задает дополнительные каталоги для поиска ссылок.|  
|[/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|Делает сведения о типах COM в указанных сборках доступными для проекта.|  
|[/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|Включает указанные файлы ресурсов в эту сборку.|  
|[/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|Задает тип, содержащий точку входа (все другие возможные точки входа игнорируются).|  
|[/moduleassemblyname](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)|Указывает сборку, к неоткрытым типам которой может обращаться .netmodule.|  
|`/modulename:<string>`|Укажите имя исходного модуля.|  
|[/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|Указывает, что компилятор не должен автоматически включать файл CSC.RSP.|  
|[/nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|Запрещает отображение сообщения компилятора об авторских правах.|  
|[/nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|Указывает компилятору не ссылаться на стандартную библиотеку (mscorlib.dll).|  
|[/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|Отключает определенные предупреждающие сообщения.|  
|[/nowin32manifest](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)|Указывает компилятору не внедрять манифест приложения в исполняемый файл.|  
|[/optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|Включает или отключает оптимизацию.|  
|[/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|Задает имя выходного файла (по умолчанию это базовое имя файла с классом main или имя первого файла).|  
|`/parallel[+&#124;-]`|Указывает, следует ли использовать параллельную сборку (+).|  
|[/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|Указывает имя и расположение PDB-файла.|  
|[/platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|Ограничивает платформу выполнения кода: x86, Itanium, x64, anycpu или anycpu32bitpreferred. Значение по умолчанию — anycpu.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Задает язык, используемый для вывода компилятора.|  
|[/recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|Включает все файлы в текущем каталоге и подкаталогах в соответствии с заданным шаблоном.|  
|[/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|Ссылается на метаданные из указанных файлов сборки.|  
|[/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|Внедряет указанный ресурс.|  
|`/ruleset:<file>`|Укажите файл набора правил, который отключает определенные диагностики.|  
|[/subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|Задает минимальную версию подсистемы, которую может использовать исполняемый файл.|  
|[/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|Задает формат выходного файла, используя один из четырех вариантов: [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md).|  
|[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|Разрешает небезопасный ([unsafe](../../../csharp/language-reference/keywords/unsafe.md)) код.|  
|[/utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|Выводит сообщения компилятора в кодировке UTF-8.|  
|[/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|Устанавливает уровень предупреждений (0–4).|  
|[/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|Задает интерпретацию определенных предупреждений как ошибок.|  
|[/win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|Задает использование этого значка для вывода.|  
|[/win32manifest](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)|Задает пользовательский файл манифеста win32.|  
|[/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|Задает файл ресурсов win32 (RES-файл).|  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Параметры компилятора C#, упорядоченные по категориям](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)   
 [Элемент \<compiler>](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)
