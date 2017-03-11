---
title: "/sdkpath | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "sdkpath"
  - "/sdkpath"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/sdkpath - параметр компилятора [Visual Basic]"
  - "sdkpath - параметр компилятора [Visual Basic]"
  - "-sdkpath - параметр компилятора [Visual Basic]"
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /sdkpath
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает расположение библиотек Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
## Синтаксис  
  
```  
/sdkpath:path  
```  
  
## Аргументы  
 `path`  
 Папка, содержащая версии файлов mscorlib.dll и microsoft.visualbasic.dll, используемых для компиляции.  Этот путь не проверяется до загрузки.  Заключите имя каталога в кавычки \(" "\), если он содержит пробел.  
  
## Заметки  
 Параметр указывает компилятору [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] загружать файлы mscorlib.dll и microsoft.visualbasic.dll из местоположения, не используемого по умолчанию.  Параметр `/sdkpath` используется вместе с [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).  В [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] применяются различные версии поддерживаемых библиотек, чтобы предотвратить использование неподдерживаемых устройствами типов и возможностей языков.  
  
> [!NOTE]
>  Параметр `/sdkpath` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  Параметр `/sdkpath` устанавливается при загрузке проекта устройства [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Пользователь может настроить программу таким образом, чтобы компилятор выполнял компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью параметра компилятора `/vbruntime`.  Дополнительные сведения см. в разделе [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## Пример  
 В следующем примере кода компиляция файла `Myfile.vb` с [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] выполняется с помощью библиотек mscorlib.dll и microsoft.visualbasic.dll, обнаруженных в стандартной папке установки [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] на диске С.  Как правило следует использовать самую последнюю версию [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)   
 [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)