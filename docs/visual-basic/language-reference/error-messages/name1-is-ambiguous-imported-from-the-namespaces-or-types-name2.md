---
title: "&lt;имя1&gt; является неоднозначным, поскольку импортировано из пространств имен или типов &lt;имя2&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30561"
  - "bc30561"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30561"
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;имя1&gt; является неоднозначным, поскольку импортировано из пространств имен или типов &lt;имя2&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Имя указано неоднозначно, и, следовательно, конфликтует с другим именем.  В компиляторе [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] отсутствуют какие\-либо правила разрешения конфликтов имен, поэтому необходимо устранить неоднозначность вручную.  
  
 **Идентификатор ошибки**: BC30561  
  
### Чтобы исправить эту ошибку  
  
1.  Устраните неоднозначность имени, удалив операторы импорта пространства имен.  
  
2.  Проверьте полное используемое имя.  
  
## См. также  
 [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)