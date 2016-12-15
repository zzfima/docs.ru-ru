---
title: "Символ &quot;.&quot; или &quot;!&quot;, стоящий в начале оператора, может использоваться только внутри оператора &quot;With&quot; | Microsoft Docs"
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
  - "vbc30157"
  - "bc30157"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30157"
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Символ &quot;.&quot; или &quot;!&quot;, стоящий в начале оператора, может использоваться только внутри оператора &quot;With&quot;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Точка \(.\) или восклицательный знак \(\!\), который не входит в блок `With`, не имеет выражения слева.  Доступ к элементам \(`.`\) и доступ к элементам словаря \(`!`\) требует выражения, указывающего на элемент, содержащий элемент.  Это выражение должно быть расположено слева от знака доступа или являться целевым объектом блока `With`, содержащего доступ к элементу.  
  
 **Идентификатор ошибки**: BC30157  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что данный блок `With` правильно оформлен.  
  
2.  Если блок `With` отсутствует, добавьте слева от метода доступа выражение, которому присваивается значение элемента, содержащего элемент.  
  
## См. также  
 [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)   
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)