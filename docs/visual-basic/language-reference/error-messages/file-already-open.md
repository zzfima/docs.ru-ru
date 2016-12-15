---
title: "Файл уже открыт | Microsoft Docs"
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
  - "vbrID55"
dev_langs: 
  - "VB"
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Файл уже открыт
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В некоторых случаях файл необходимо закрыть прежде чем выполнять `FileOpen` или другую операцию.  Возможные причины появления этой ошибки:  
  
-   Операция `FileOpen` режима последовательного вывода была выполнена для уже открытого файла.  
  
-   Оператор ссылается на открытый файл.  
  
### Чтобы исправить эту ошибку  
  
1.  Закройте файл прежде чем выполнять оператор.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>