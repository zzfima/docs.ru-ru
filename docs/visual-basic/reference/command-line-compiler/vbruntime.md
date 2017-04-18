---
title: "/ vbruntime | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 455f950988b540b74874ce38882c59059f77ea8f
ms.lasthandoff: 03/13/2017

---
# <a name="vbruntime"></a>/vbruntime
Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Аргументы  
 \-  
 Компиляция без ссылки на библиотеку времени выполнения Visual Basic.  
  
 \+  
 Компиляция со ссылкой на значение по умолчанию библиотеки времени выполнения Visual Basic.  
  
 \*  
 Компиляция без ссылки на библиотеку времени выполнения Visual Basic и внедрения в сборку базовую функциональность библиотеки времени выполнения Visual Basic.  
  
 `path`  
 Компиляция со ссылкой на указанную библиотеку (DLL).  
  
## <a name="remarks"></a>Примечания  
 `/vbruntime` Параметр компилятора позволяет указать, что компилятор должен компилировать без ссылки на библиотеку времени выполнения Visual Basic. Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения регистрируются на код или языковой конструкции, которые создает вызов вспомогательной среды выполнения Visual Basic. (Объект *Вспомогательная среда выполнения Visual Basic* является функцией, определяемой в Microsoft.VisualBasic.dll, которая вызывается во время выполнения, чтобы выполнить конкретную семантику языка.)  
  
 `/vbruntime+` Параметр создает такое же поведение, которое возникает, если не `/vbruntime` указан ключ. Можно использовать `/vbruntime+` могут переопределить предыдущих `/vbruntime` коммутаторов.  
  
 Большинство объектов `My` тип недоступны при использовании `/vbruntime-` или `vbruntime:``path` параметры.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Внедрение основные функциональные возможности среды выполнения Visual Basic  
 `/vbruntime*` Вариант позволяет выполнять компиляцию без ссылки на библиотеку времени выполнения. Вместо этого основных функций из библиотеки времени выполнения Visual Basic внедренного в сборку пользователя. Этот параметр можно использовать, если приложение выполняется на платформах, которые не содержат среда выполнения Visual Basic.  
  
 Внедренные следующие компоненты времени выполнения:  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions>класс</xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>метод</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>метод</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>метод</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack>Константа</xref:Microsoft.VisualBasic.Constants.vbBack>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr>Константа</xref:Microsoft.VisualBasic.Constants.vbCr>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf>Константа</xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed>Константа</xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf>Константа</xref:Microsoft.VisualBasic.Constants.vbLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine>Константа</xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar>Константа</xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString>Константа</xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab>Константа</xref:Microsoft.VisualBasic.Constants.vbTab>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>Константа</xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
-   Некоторые объекты `My` типа  
  
 Если компиляция выполняется с помощью `/vbruntime*` параметр и код ссылается на элемент из библиотеки времени выполнения Visual Basic, который не внедрен с основными функциями, компилятор возвращает ошибку, указывающую, что элемент недоступен.  
  
## <a name="referencing-a-specified-library"></a>Ссылка на указанную библиотеку  
 Можно использовать `path` аргумент для компиляции со ссылкой на библиотеку настраиваемую среду выполнения вместо библиотеки времени выполнения Visual Basic по умолчанию.  
  
 Если значение `path` аргумент — полный путь к библиотеке DLL, компилятор будет использовать этот файл как библиотеку среды выполнения. Если значение `path` аргумент не является полный путь к библиотеке DLL, компилятор Visual Basic будет сначала поиск идентифицированной библиотеки DLL в текущей папке. Затем выполнит поиск по пути, указанному с помощью [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) параметр компилятора. Если `/sdkpath` не используется параметр компилятора, компилятор будет искать идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `/vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>См. также  
 [Visual Basic Core — новый режим компиляции в Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
