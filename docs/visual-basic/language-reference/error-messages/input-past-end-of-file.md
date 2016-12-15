---
title: "Оператор Input обнаружил конец файла | Microsoft Docs"
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
  - "vbrID62"
dev_langs: 
  - "VB"
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Input обнаружил конец файла
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `Input` выполняет чтение из пустого файла или из файла, все данные которого уже были использованы, либо из файла, открытого для двоичного доступа или была использована функция `EOF`.  
  
### Чтобы исправить эту ошибку  
  
1.  Используйте функцию `EOF` непосредственно перед оператором `Input`, чтобы определить конец файла.  
  
2.  Если файл открыт для двоичного доступа, используйте `Seek` и `Loc`.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>