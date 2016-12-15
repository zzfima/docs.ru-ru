---
title: "Метод не имеет подписи, совместимой с делегатом | Microsoft Docs"
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
  - "bc36563"
  - "vbc36563"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36563"
ms.assetid: 3ca8b873-e98d-419b-95f2-d75bd2a9eb6c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Метод не имеет подписи, совместимой с делегатом
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Существует несоответствие между сигнатурами метода и делегата, которые вы пытаетесь использовать.  Типы параметров и значения, возвращаемые классом делегата, определяются оператором `Delegate`.  Для создания экземпляра класса данного делегата может использоваться любая процедура с соответствующими типами параметров и типом возвращаемого значения.  
  
 **Идентификатор ошибки**: BC36563  
  
## См. также  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Разрешение перегрузки](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)