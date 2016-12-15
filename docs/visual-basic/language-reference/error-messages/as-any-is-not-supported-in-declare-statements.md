---
title: "&#39;As Any&#39; не поддерживается в операторах Declare | Microsoft Docs"
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
  - "bc30828"
  - "vbc30828"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30828"
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;As Any&#39; не поддерживается в операторах Declare
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип данных `Any` использовался с операторами `Declare` в Visual Basic 6.0 и более ранних версий для того, чтобы разрешить использование аргументов, которые могли содержать любой тип данных.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] поддерживает перегрузку, однако это делает тип данных `Any` устаревшим.  
  
 **Идентификатор ошибки:** BC30828  
  
### Чтобы исправить эту ошибку  
  
1.  В объявлениях параметров укажите конкретный используемый тип, например:  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Используйте атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> для указания `As Any`, когда вызываемой процедурой ожидается `Void*`.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Пошаговое руководство. Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Creating Prototypes in Managed Code](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)