---
title: Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c1b57ccdaa9e04c837ecf7572bc164683a934b2d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273521"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
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
