---
title: "/vbruntime | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbruntime"
  - "/vbruntime"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/vbruntime - параметр компилятора [Visual Basic]"
  - "vbruntime - параметр компилятора [Visual Basic]"
  - "-vbruntime - параметр компилятора [Visual Basic]"
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /vbruntime
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что компилятор должен компилировать без ссылки на библиотеку времени выполнения Visual Basic, или со ссылкой на конкретную библиотеку времени выполнения.  
  
## Синтаксис  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## Аргументы  
 \-  
 Компиляция без ссылки на библиотеку времени выполнения Visual Basic.  
  
 \+  
 Компиляция со ссылкой на библиотеку времени выполнения Visual Basic, установленную по умолчанию.  
  
 \*  
 Компилирует без ссылки на библиотеку времени выполнения Visual Basic, включая в сборку базовую функциональность библиотеки времени выполнения Visual Basic.  
  
 `path`  
 Компиляция со ссылкой на указанную библиотеку \(DLL\).  
  
## Заметки  
 Параметр компилятора `/vbruntime` позволяет определить компиляцию без ссылки на библиотеку времени выполнения Visual Basic.  Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, то в коде или конструкциях языка могут возникнуть ошибки и предупреждения, которые генерируют вызов вспомогательной среды выполнения Visual Basic.  \(*Вспомогательная среда выполнения Visual Basic* — это функция, определённая в Microsoft.VisualBasic.dll, которая вызывается во время выполнения, чтобы выполнить конкретную семантику языка.\)  
  
 Параметр `/vbruntime+` ведет себя так же, как если не указан ключ `/vbruntime`.  Можно использовать параметр `/vbruntime+` для переопределения предыдущих ключей `/vbruntime`.  
  
 Большинство объектов типа `My` недоступна при использовании `/vbruntime-` или параметры `vbruntime:``path`.  
  
## Внедрение основных функциональных возможностей среды выполнения Visual Basic  
 Параметр `/vbruntime*` позволяет компиляцию без ссылки на библиотеку времени выполнения.  Вместо этого основные функции из библиотеки времени выполнения Visual Basic внедряются в пользовательскую сборку.  Этот параметр можно использовать, если приложение работает на платформах, которые не содержат среды выполнения Visual Basic.  
  
 Встроены следующие члены среды выполнения:  
  
-   Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbBack>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbCr>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbLf>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbTab>  
  
-   Константа <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
-   Некоторые объекты типа `My`  
  
 Если при компиляции с использованием параметра`/vbruntime*` , и ваш код ссылается на член из библиотеки времени выполнения Visual Basic, не встроенного в базовую функциональность, компилятор возвращает сообщение об ошибке, которое указывает, что член не доступен.  
  
## Ссылка на определенную библиотеку  
 Можно использовать аргумент `path` для компиляции со ссылкой на пользовательскую библиотеку времени выполнения вместо библиотеки времени выполнения Visual Basic, установленной по умолчанию.  
  
 Если значение для аргумента `path` равно полному пути к DLL\-файлу, компилятор будет использовать этот файл как библиотеку среды выполнения.  Если значение аргумента `path` содержит неполный путь к DLL\-файлу, то компилятор Visual Basic будет сначала производить поиск идентифицированной библиотеки DLL в текущей папке.  Затем будет выполнен поиск по пути, указанному с помощью параметра компилятора [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).  Если параметр компилятора `/sdkpath` не используется, поиск идентифицированной библиотеки DLL будет осуществляться в папке .NET Framework \(`%systemroot%\Microsoft.NET\Framework\versionNumber`\).  
  
## Пример  
 В следующем примере показано использование параметра `/vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## См. также  
 [Visual Basic Core — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1 \(SP1\)](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)