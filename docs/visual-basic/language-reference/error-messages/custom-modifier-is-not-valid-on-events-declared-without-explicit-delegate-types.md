---
title: "&#39; Настраиваемый &#39; модификатор недопустим для событий, объявленных без явных делегируемых типов"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords: BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 844bd033ea05e373b04a04f80777af77179c1263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39; Настраиваемый &#39; модификатор недопустим для событий, объявленных без явных делегируемых типов
В отличие от событий от обычного `Custom Event` объявления требуется `As` предложение после имени события, которое явно указывает тип делегата для события.  
  
 Обычные события могут быть определены с `As` предложения и явного типа делегата или списка параметров сразу после имени события.  
  
 **Идентификатор ошибки:** BC31122  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите делегат с тем же списком параметров, что пользовательское событие.  
  
     Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, то соответствующий делегат будет следующим.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Замените список параметров пользовательского события с `As` предложение указания типа делегата.  
  
     В примере `Custom Event` объявления можно переписать следующим образом.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере объявляется `Custom Event` и указывает необходимые `As` предложения с типом делегата.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)
