---
title: "/resource (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/res - параметр компилятора [Visual Basic]"
  - "/resource - параметр компилятора [Visual Basic]"
  - "res - параметр компилятора [Visual Basic]"
  - "-res - параметр компилятора [Visual Basic]"
  - "resource - параметр компилятора [Visual Basic]"
  - "-resource - параметр компилятора [Visual Basic]"
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /resource (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Внедряет управляемый ресурс в сборку.  
  
## Синтаксис  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`filename`|Обязательный.  Файл ресурсов, внедряемый в выходной файл.  По умолчанию файл `filename` в составе сборки является общедоступным.  Если имя файла содержит пробел, следует заключить его в кавычки \(" "\).|  
|`identifier`|Необязательный.  Логическое имя ресурса, используемое для его загрузки.  По умолчанию используется имя файла.  Также можно указать, открыт или закрыт ресурс в манифесте сборки, например: `/res:``filename.res`, `myname.res`, `public`|  
  
## Заметки  
 Чтобы связать ресурс и сборку, не помещая файл ресурсов в выходной файл, используется параметр `/linkresource`.  
  
 Если `filename` является файлом ресурсов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], созданным, например, с помощью [Resgen.exe \(Resource File Generator\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources> \(дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>\).  Чтобы получить доступ ко всем остальным ресурсам во время выполнения, воспользуйтесь одним из следующих средств: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 `/res` является короткой формой `/resource` .  
  
 Дополнительные сведения о настройке `/resource` в Visual Studio IDE [Управление ресурсами приложения \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
## Пример  
 Следующий код компилирует `In.vb` и присоединяет к нему файл ресурсов `Rf.resource`.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)