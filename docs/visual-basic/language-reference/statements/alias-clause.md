---
title: "Предложение Alias (Visual Basic) | Microsoft Docs"
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
  - "vb.Alias"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Alias - ключевое слово"
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Alias (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что внешняя процедура имеет другое имя в своей DLL.  
  
## Заметки  
 Ключевое слово `Alias` можно использовать в следующем контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 В следующем примере ключевое слово `Alias` используется для указания имени функции в advapi32.dll \(`GetUserNameA`\) на месте которой в этом примере используется `getUserName`.  Функция `getUserName` называется вместо этого `getUser` и отображает имя текущего пользователя.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)