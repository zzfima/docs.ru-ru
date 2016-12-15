---
title: "Слишком длинный идентификатор | Microsoft Docs"
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
  - "bc30033"
  - "vbc30033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30033"
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Слишком длинный идентификатор
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Имя или идентификатор любого программируемого элемента ограничен 1023 символами.  Кроме того, полное имя не может превышать длину в 1023 символа.  Это означает, что вся строка идентификатора \(`<namespace>.<...>.<namespace>.<class>.<element>`\) не может включать более 1023 знаков, включая символы оператора доступа к членам \(`.`\).  
  
 **Идентификатор ошибки:** BC30033  
  
### Чтобы исправить эту ошибку  
  
-   Уменьшите длину идентификатора.  
  
## См. также  
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)