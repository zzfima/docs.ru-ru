---
title: "/linkresource (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/linkres - параметр компилятора [Visual Basic]"
  - "/linkresource - параметр компилятора [Visual Basic]"
  - "linkres - параметр компилятора [Visual Basic]"
  - "-linkres - параметр компилятора [Visual Basic]"
  - "linkresource - параметр компилятора [Visual Basic]"
  - "-linkresource - параметр компилятора [Visual Basic]"
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /linkresource (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Создает ссылку на управляемый ресурс.  
  
## Синтаксис  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## Аргументы  
 `filename`  
 Обязательный.  Файл ресурсов, присоединяемый к сборке.  Заключите имя файла в кавычки \(" "\), если оно содержит пробел.  
  
 `identifier`  
 Необязательный.  Логическое имя ресурса.  Имя, используемое для загрузки ресурса.  По умолчанию используется имя файла.  Дополнительно можно указать, является ли файл public или private в манифесте сборки. Например:`/linkres:filename.res,myname.res,public`.  По умолчанию файл `filename` в составе сборки является общедоступным.  
  
## Заметки  
 Параметр `/linkresource` не включает файл ресурса в выходной файл; для этой цели следует использовать параметр `/resource`.  
  
 Параметр  `/linkresource` требует одного из параметров `/target`, отличного от `/target:module`.  
  
 Если `filename` является [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файлом ресурсов, созданным, например, в помощью [Resgen.exe \(Resource File Generator\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) или в среде разработки, то к нему можно получить доступ с использованием членов пространства имен <xref:System.Resources>.  \(Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.\) Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы, которые начинаются с `GetManifestResource` в классе <xref:System.Reflection.Assembly>.  
  
 Имя файла может иметь любой формат.  Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.  
  
 Сокращенная форма `/linkresource` — `/linkres`.  
  
> [!NOTE]
>  Параметр `/linkresource` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## Пример  
 Следующий код компилирует `In.vb` и связывает с файлом ресурсов `Rf.resource`.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)