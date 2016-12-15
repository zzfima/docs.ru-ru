---
title: "/utf8output (Visual Basic) | Microsoft Docs"
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
  - "/utf8output - параметр компилятора [Visual Basic]"
  - "utf8output - параметр компилятора [Visual Basic]"
  - "-utf8output - параметр компилятора [Visual Basic]"
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /utf8output (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Отображает выходные данные компилятора в кодировке UTF\-8.  
  
## Синтаксис  
  
```  
/utf8output[+ | -]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Необязательный.  Значение по умолчанию `/utf8output-` не используется в выходном файле, созданном компилятором.  Указание `/utf8output` совпадает с указанием `/utf8output+`.  
  
## Заметки  
 В некоторых конфигурациях для различных языков выходные данные компилятора могут неправильно отображаться на консоли.  В этом случае следует использовать параметр `/utf8output` и записывать выходные данные компилятора в файл.  
  
> [!NOTE]
>  Параметр `/utf8output` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## Пример  
 Следующий код компилирует `In.vb` и направляет компилятор для отображения вывода в кодировке UTF\-8.  
  
```  
vbc /utf8output in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)