---
title: "/help, /? (Visual Basic) | Microsoft Docs"
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
  - "/? - параметр компилятора [Visual Basic]"
  - "/help - параметр компилятора [Visual Basic]"
  - "? параметр компилятора [Visual Basic]"
  - "-? - параметр компилятора [Visual Basic]"
  - "help - параметр компилятора [Visual Basic]"
  - "-help - параметр компилятора [Visual Basic]"
ms.assetid: eb984aa5-ac98-4d0b-a0d2-24238d7bc8dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /help, /? (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Отображает список параметров компилятора.  
  
## Синтаксис  
  
```  
/help  
' -or-  
/?  
```  
  
## Заметки  
 Если данный параметр содержится в командной строке, выходной файл не создается и компиляция не производится.  
  
> [!NOTE]
>  Параметр `/help` недоступен из среды разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]; он доступен только при компиляции из командной строки.  
  
## Пример  
 Данный пример кода демонстрирует вывод справки из командной строки:  
  
```  
vbc /help  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)