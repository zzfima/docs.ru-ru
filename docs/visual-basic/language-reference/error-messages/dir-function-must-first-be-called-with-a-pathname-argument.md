---
title: "Функция Dir должна первый раз вызываться с аргументом PathName | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrDIR_IllegalCall"
dev_langs: 
  - "VB"
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Функция Dir должна первый раз вызываться с аргументом PathName
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Исходный вызов функции `Dir` не включает аргумент `PathName`.  Первый вызов функции `Dir` должен включать `PathName`, но последующие вызовы функции `Dir` необязательно должны включать параметры для извлечения следующего элемента.  
  
### Чтобы исправить эту ошибку  
  
1.  Вставьте аргумент `PathName` в вызов функции.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>