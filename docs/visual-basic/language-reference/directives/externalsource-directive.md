---
title: "Директива #ExternalSource | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#Externalsource"
  - "#ExternalSource"
  - "vb.ExternalSource"
  - "Externalsource"
  - "vb.#ExternalSource"
  - "ExternalSource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#ExternalSource - директива"
  - "ExternalSource - директива (#ExternalSource)"
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: 160
caps.handback.revision: 160
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Директива #ExternalSource
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает сопоставление между определенными строками исходного кода и текстом, внешним по отношению к источнику.  
  
## Синтаксис  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## Части  
 `StringLiteral`  
 Путь к внешнему источнику.  
  
 `IntLiteral`  
 Номер первой строки внешнего источника.  
  
 `LogicalLine`  
 Строка внешнего источника, в которой возникла ошибка.  
  
 `#End ExternalSource`  
 Завершает блок `#ExternalSource`.  
  
## Заметки  
 Эта директива используется только компилятором и отладчиком.  
  
 Исходный файл может содержать директивы внешнего источника, которые задают сопоставление между определенными строками кода исходного файла и текстом, внешним по отношению к источнику, например файлом ASPX.  Если в указанном исходном коде во время компиляции возникли ошибки, то они определяются как появившиеся из внешнего источника.  
  
 Директивы внешнего источника не влияют на компиляцию и не могут быть вложенными.  Они предназначены только для внутреннего использования приложениями.  
  
## См. также  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)