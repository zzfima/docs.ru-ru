---
title: '&#39;Настраиваемый&#39; модификатор недопустим для событий, объявленных без явных делегируемых типов'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;Настраиваемый&#39; модификатор недопустим для событий, объявленных без явных делегируемых типов
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
