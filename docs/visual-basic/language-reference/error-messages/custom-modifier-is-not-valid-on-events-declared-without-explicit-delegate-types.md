---
title: '&#39;Custom&#39; модификатор недопустим для событий, объявленных без явных делегируемых типов'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c909973ef1c00cb01179b0e5527dfecd6f41e577
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574785"
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;Custom&#39; модификатор недопустим для событий, объявленных без явных делегируемых типов
В отличие от событий ненастраиваемых `Custom Event` требует `As` предложение после имени события, которая явно задает тип делегата для события.  
  
 Обычные события могут быть определены с `As` предложение и явный тип делегата или списка параметров сразу после имени события.  
  
 **Идентификатор ошибки:** BC31122  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите делегат с такой же список параметров, как пользовательское событие.  
  
     Например если `Custom Event` определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, а затем соответствующий делегат будет следующим.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Замените список параметров пользовательского события с `As` предложение, определяющее тип делегата.  
  
     В примере `Custom Event` объявление можно переписать следующим образом.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере объявляется `Custom Event` и указывает необходимые `As` предложение с типом делегата.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>См. также
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
