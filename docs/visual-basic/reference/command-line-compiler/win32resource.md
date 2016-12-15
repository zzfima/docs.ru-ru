---
title: "/win32resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/win32resource"
  - "win32resource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32resource - параметр компилятора [Visual Basic]"
  - "win32resource - параметр компилятора [Visual Basic]"
  - "-win32resource - параметр компилятора [Visual Basic]"
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32resource
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Включает файл ресурсов Win32 в выходной файл.  
  
## Синтаксис  
  
```  
/win32resource:filename  
```  
  
## Аргументы  
 `filename`  
 Имя файла ресурсов, который добавляется в выходной файл.  Если имя файла содержит пробел, следует заключить его в кавычки \(" "\).  
  
## Заметки  
 Файл ресурсов Win32 можно создать с помощью компилятора ресурсов Microsoft Windows Resource Compiler \(RC\).  
  
 Файл ресурсов Win32 может содержать сведения о версии или растрового изображения \(значков\), которые определяют приложение в **\*\*\* В обозревателе файла \*\*\*** справки.  Если параметр `/win32resource` не указан, то компилятор формирует сведения о версии на основе версии сборки.  Параметры `/win32resource` и `/win32icon` являются взаимоисключающими.  
  
 Сведения о создании ссылки на файл ресурсов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] см. в разделе [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md), а сведения о присоединении файла ресурсов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] — в разделе [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md).  
  
> [!NOTE]
>  Параметр `/win32resource` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  
  
## Пример  
 Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)