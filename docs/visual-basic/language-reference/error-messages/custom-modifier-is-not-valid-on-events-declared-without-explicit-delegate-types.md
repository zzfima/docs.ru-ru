---
title: "Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31122"
  - "bc31122"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31122"
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В отличие от обычного события для объявления `Custom Event` необходимо указать предложение `As` после имени события, которое явно указывает тип делегата для события.  
  
 Обычные события могут быть определены с помощью предложения `As` и явного типа делегата или списка параметров, следующего сразу после имени события.  
  
 **Идентификатор ошибки**: BC31122  
  
### Чтобы исправить эту ошибку  
  
1.  Определите делегат с тем же списком параметров, как у пользовательского события.  
  
     Например, если `Custom Event` было определено с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, то соответствующий делегат будет такой, как приведен ниже.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/custom-modifier-is-not-v_1.vb)]  
  
2.  Замените список параметров пользовательского события с помощью предложения `As`, задающего тип делегата.  
  
     Объявление `Custom Event` в примере можно переписать следующим образом.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/custom-modifier-is-not-v_2.vb)]  
  
## Пример  
 В этом примере объявляется `Custom Event` и указывается требуемое предложение `As` с типом делегата.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/custom-modifier-is-not-v_3.vb)]  
  
## См. также  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)