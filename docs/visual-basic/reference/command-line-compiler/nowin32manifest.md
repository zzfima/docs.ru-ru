---
title: "/nowin32manifest (Visual Basic) | Microsoft Docs"
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
  - "/nowin32manifest - параметр компилятора [Visual Basic]"
  - "nowin32manifest - параметр компилятора [Visual Basic]"
  - "-nowin32manifest - параметр компилятора [Visual Basic]"
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# /nowin32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что компилятор не может внедрить какой–либо манифест приложения в исполняемый файл.  
  
## Синтаксис  
  
```  
/nowin32manifest  
```  
  
## Заметки  
 Если эта опция используется, приложение будет предметом для виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах построения.  Дополнительные сведения о виртуализации см. в разделе [Развертывание ClickOnce в Windows Vista](/visual-studio/deployment/clickonce-deployment-on-windows-vista).  
  
 Дополнительные сведения о создании манифестов см. в разделе [\/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md).  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)