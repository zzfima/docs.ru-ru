---
title: "/help, /? (Visual Basic) | Microsoft Docs"
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
  - "/? - параметр компилятора [Visual Basic]"
  - "/help - параметр компилятора [Visual Basic]"
  - "? параметр компилятора [Visual Basic]"
  - "-? - параметр компилятора [Visual Basic]"
  - "help - параметр компилятора [Visual Basic]"
  - "-help - параметр компилятора [Visual Basic]"
ms.assetid: eb984aa5-ac98-4d0b-a0d2-24238d7bc8dc
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /help, /? (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

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
>  Параметр `/help` недоступен из среды разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]; он доступен только при компиляции из командной строки.  
  
## Пример  
 Данный пример кода демонстрирует вывод справки из командной строки:  
  
```  
vbc /help  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)