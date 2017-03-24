---
title: "/ Target (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ccdb87188b924303057d5867dccece937defe74d
ms.lasthandoff: 03/13/2017

---
# <a name="target-visual-basic"></a>/target (Visual Basic)
Задает формат выходных данных компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице перечислены эффект `/target` параметр.  
  
|**Параметр**|**Поведение**|  
|----------------|------------------|  
|`/target:exe`|Указывает компилятору создавать исполняемое консольное приложение.<br /><br /> Это параметр по умолчанию, если не `/target` параметра. Исполняемый файл создается с расширением .exe.<br /><br /> Если не указано иначе с `/out` параметр, выходной файл получает имя входного файла, который содержит `Sub Main` процедуры.<br /><br /> Только один `Sub Main` необходимые процедуры в файлах исходного кода, которые компилируются в файл .exe. Используйте `/main` параметр компилятора, чтобы указать, какой класс содержит `Sub Main` процедуры.|  
|`/target:library`|Указывает компилятору создать библиотеку динамической компоновки (DLL).<br /><br /> Файл динамической библиотеки создается с расширением DLL.<br /><br /> Если не указано иначе с `/out` параметр, выходной файл получает имя первого входного файла.<br /><br /> При построении библиотеки DLL, `Sub Main` процедура не является обязательной.|  
|`/target:module`|Указывает компилятору создавать модуль, который может быть добавлен в сборку.<br /><br /> Выходной файл создается с расширением .netmodule.<br /><br /> .NET общеязыковая среда выполнения не удается загрузить файл, не содержащий сборки. Тем не менее, можно включить такой файл в манифест сборки с помощью `/reference`.<br /><br /> Если код одного модуля ссылается на внутренние типы другого модуля, оба модуля должны быть включены в манифест сборки с помощью `/reference`.<br /><br /> [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.|  
|`/target:winexe`|Указывает компилятору создать исполняемый файл приложения на основе Windows.<br /><br /> Исполняемый файл создается с расширением .exe. Приложения Windows, которое предоставляет пользовательский интерфейс, либо из [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] библиотеки классов или интерфейсов API Win32.<br /><br /> Если не указано иначе с `/out` параметр, выходной файл получает имя входного файла, который содержит `Sub Main` процедуры.<br /><br /> Только один `Sub Main` необходимые процедуры в файлах исходного кода, которые компилируются в файл .exe. В случаях, когда ваш код более одного класса, имеющего `Sub Main` процедуры, используйте `/main` параметр компилятора, чтобы указать, какой класс содержит `Sub Main` процедуры|  
|`/target:appcontainerexe`|Указывает компилятору создать исполняемый файл приложения под управлением Windows, необходимо запустить в контейнере приложения. Этот параметр предназначен для [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)] приложений.<br /><br /> **Appcontainerexe** параметр устанавливает бит в поле характеристики [переносимый исполняемый файл](http://go.microsoft.com/fwlink/p/?LinkId=236960) файла. Этот бит указывает, что приложение должно работать в контейнере приложения. Если этот бит задан, если возникает ошибка `CreateProcess` метод пытается запустить приложение вне контейнера приложения. Помимо этот бит параметр **/target: appcontainerexe** эквивалентно **/target: winexe**.<br /><br /> Исполняемый файл создается с расширением .exe.<br /><br /> Если не задано иное, используя `/out` параметр, выходной файл получает имя входного файла, который содержит `Sub Main` процедуры.<br /><br /> Только один `Sub Main` необходимые процедуры в файлах исходного кода, которые компилируются в файл .exe. Если код содержит несколько классов с `Sub Main` процедуры, используйте `/main` параметр компилятора, чтобы указать, какой класс содержит `Sub Main` процедуры|  
|`/target:winmdobj`|Указывает компилятору создать промежуточный файл, который можно преобразовать в бинарный winmd-файл среды выполнения Windows. Winmd-файл можно использовать с JavaScript и C++, в дополнение к программам программ на управляемом языке.<br /><br /> Промежуточный файл создается с расширением .winmdobj.<br /><br /> Если не задано иное, используя `/out` параметр, выходной файл получает имя первого входного файла. A `Sub Main` процедуры не требуется.<br /><br /> Winmdobj-файл предназначен для использования в качестве входных данных для <xref:Microsoft.Build.Tasks.WinMDExp>инструмента для создания файла метаданных (WinMD) Windows экспорта.</xref:Microsoft.Build.Tasks.WinMDExp> WinMD-файл имеет расширение .winmd и содержит код из исходной библиотеки и определения WinMD, JavaScript, C++ и использования средой выполнения Windows.|  
  
 Если не указать `/target:module`, `/target` вызывает [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] манифест сборки, добавляется в выходной файл.  
  
 Каждый экземпляр Vbc.exe приводит, максимум один выходной файл. При указании параметра компилятора `/out` или `/target` более одного раза, последний процессы компиляции, вступили в силу. Сведения о всех файлах компиляции добавлен в манифест. Все выходные файлы, за исключением случаев, которые были созданы с `/target:module` содержат метаданные сборки в манифесте. Используйте [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1) для просмотра метаданных в выходной файл.  
  
 Краткая форма `/target` — `/t`.  
  
### <a name="to-set-target-in-the-visual-studio-ide"></a>Чтобы установить параметр/target в Интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Приложение** .  
  
3.  Измените значение в **тип приложения** поле.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `in.vb`, создавая `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/ addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [/ moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)   
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
