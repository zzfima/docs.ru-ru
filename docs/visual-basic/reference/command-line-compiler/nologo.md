---
title: "/nologo (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "/nologo - параметр компилятора [Visual Basic]"
  - "баннеры, отключение при загрузке"
  - "nologo - параметр компилятора [Visual Basic]"
  - "-nologo - параметр компилятора [Visual Basic]"
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /nologo (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Отменяет отображение авторских прав и дополнительных сообщений при компиляции.  
  
## Синтаксис  
  
```  
/nologo  
```  
  
## Заметки  
 При задании `/nologo` компилятор не отображает заголовок, содержащий сведения об авторских правах.  По умолчанию параметр `/nologo` не действует.  
  
> [!NOTE]
>  Параметр `/nologo` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  
  
## Пример  
 В следующем коде компилируется `T2.vb` без отображения заголовка, содержащего сведения об авторских правах.  
  
```  
vbc /nologo t2.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)