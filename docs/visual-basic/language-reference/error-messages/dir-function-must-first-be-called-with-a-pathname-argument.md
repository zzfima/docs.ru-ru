---
title: "Функция Dir должна первый раз вызываться с аргументом PathName | Microsoft Docs"
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
  - "vbrDIR_IllegalCall"
dev_langs: 
  - "VB"
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Функция Dir должна первый раз вызываться с аргументом PathName
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Исходный вызов функции `Dir` не включает аргумент `PathName`.  Первый вызов функции `Dir` должен включать `PathName`, но последующие вызовы функции `Dir` необязательно должны включать параметры для извлечения следующего элемента.  
  
### Чтобы исправить эту ошибку  
  
1.  Вставьте аргумент `PathName` в вызов функции.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>