---
title: "Недопустимое соглашение при вызове DLL | Microsoft Docs"
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
  - "vbrID49"
dev_langs: 
  - "VB"
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Недопустимое соглашение при вызове DLL
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Аргументы, передаваемые в DLL, должны совпадать с аргументами, ожидаемыми подпрограммой из библиотеки DLL.  Соглашения о вызовах регламентируют количество, тип и порядок следования аргументов.  Возможно, программа вызывает другую подпрограмму в DLL, которой передается неправильный тип или количество аргументов.  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что все типы аргументов совпадают с типами, указанными в объявлении вызываемой подпрограммы из библиотеки DLL.  
  
2.  Убедитесь, что число передаваемых аргументов совпадает с числом, указанным в объявлении вызываемой подпрограммы из библиотеки DLL.  
  
3.  Если программа DLL ожидает передачи аргументов по значению, убедитесь, что в объявлении подпрограммы из библиотеки DLL для этих аргументов задан параметр `ByVal`.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)