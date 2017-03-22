---
title: "Смягчается преобразование делегата (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c0160165d3df9755481b89570b4cd135b3a990a2
ms.lasthandoff: 03/13/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Неявное преобразование делегата (Visual Basic)
Неявное преобразование делегата позволяет присваивать делегатам обработчики, подпрограммы и функции, даже в том случае, когда их подписи не идентичны. Таким образом привязка к делегату становится согласованной с привязкой уже разрешенной в вызове метода.  
  
## <a name="parameters-and-return-type"></a>Параметры и тип возвращаемого значения  
 Вместо сопоставления точной подписи ослабленное преобразование требует соблюдение следующих условий при `Option Strict` задано значение `On`:  
  
-   Должно существовать расширяющее преобразование типа данных каждого параметра делегата к типу данных соответствующего параметра назначенной функции или `Sub`. В следующем примере делегат `Del1` имеет один параметр `Integer`. Параметр `m` в назначенный лямбда-выражения должны иметь тип данных, для которых имеется расширяющее преобразование из `Integer`, такие как `Long` или `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates&#2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Сужающие преобразования разрешены только тогда, когда `Option Strict` равен `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates №&8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Должно существовать расширяющее преобразование в обратном направлении из возвращаемого типа назначенной функции или `Sub` в возвращаемый тип делегата. В следующих примерах тело каждого назначенного лямбда-выражения должно иметь тип данных, который может быть расширен до `Integer` , так как возвращаемый тип `del1` — `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates&#3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Если `Option Strict` равен `Off`, расширяющее ограничение удаляется в обоих направлениях.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>Пропуск параметра спецификации  
 Ослабленные делегаты также позволяют полностью опустить параметры спецификации в назначенном методе:  
  
 [!code-vb[VbVbalrRelaxedDelegates&#5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates №&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Обратите внимание, что нельзя задать некоторые параметры и указать другие.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 Возможность опустить параметры является полезным в ситуации, например при определении обработчика событий, в которых участвуют несколько сложных параметров. Аргументы для некоторых обработчиков событий не используются. Вместо этого обработчик непосредственно получает состояние элемента управления, на котором регистрируется событие, а аргументы игнорируются. Ослабленные делегаты позволяют опустить аргументы в таких объявлениях, когда результат неоднозначен. В следующем примере полностью заданный метод `OnClick` можно переписать в виде `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Примеры AddressOf  
 Лямбда-выражения используются в предыдущих примерах облегчает связи типа см. Однако ослабление разрешено для назначений делегата, использующих `AddressOf`, `Handles`, или `AddHandler`.  
  
 В следующем примере функции `f1`, `f2`, `f3`, и `f4` могут быть назначены `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates №&9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 Следующий пример доступен, только если `Option Strict` равен `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Игнорирование возвращаемого значения функции  
 Неявное преобразование делегата позволяет назначить функцию `Sub` делегатом, фактически независимо от возвращаемого значения функции. Тем не менее, нельзя назначить `Sub` делегату функции. В следующем примере адрес функции `doubler` назначается `Sub` делегат `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Практическое руководство: передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
