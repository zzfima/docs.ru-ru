---
title: Неявное преобразование делегата (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650833"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Неявное преобразование делегата (Visual Basic)
Неявное преобразование делегата позволяет присваивать делегатам обработчики, подпрограммы и функции, даже в том случае, если их подписи не совпадают. Таким образом привязка к делегату становится согласованной с привязкой уже разрешенной в вызове метода.  
  
## <a name="parameters-and-return-type"></a>Параметры и тип возвращаемого значения  
 Вместо сопоставления точной подписи ослабленное преобразование требует соблюдение следующих условий при `Option Strict` равно `On`:  
  
-   Должно существовать расширяющее преобразование из типа данных каждого параметра делегата к типу данных соответствующего параметра назначенной функции или `Sub`. В следующем примере делегат `Del1` имеет один параметр `Integer`. Параметр `m` в назначенный лямбда-выражения должны иметь тип данных, для которого имеется расширяющее преобразование из `Integer`, такие как `Long` или `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Сужающие преобразования разрешены только если `Option Strict` равно `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Должно существовать расширяющее преобразование в обратном направлении из возвращаемого типа назначенной функции или `Sub` в возвращаемый тип делегата. В следующих примерах тело каждого назначенного лямбда-выражения должно иметь тип данных, который расширяется до `Integer` , так как возвращаемый тип `del1` — `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Если `Option Strict` равно `Off`, расширяющие ограничение удаляется в обоих направлениях.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>Пропуск параметра спецификации  
 Ослабленные делегаты также позволяют полностью опустить параметры спецификации в назначенном методе:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Обратите внимание, что нельзя задать некоторые параметры и указать другие.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 Возможность опустить параметры полезна в ситуации, например при определении обработчика событий, где участвуют несколько сложных параметров. Аргументы для некоторых обработчиков событий не используются. Вместо этого обработчик непосредственно получает состояние элемента управления, на котором регистрируется событие и игнорирует аргументы. Ослабленные делегаты позволяют опустить аргументы в таких объявлениях, когда результат неоднозначен. В следующем примере полностью заданный метод `OnClick` можно переписать так, как `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Примеры AddressOf  
 Для связи между типами простой см. в предыдущих примерах используются лямбда-выражения. Однако ослабление разрешено для назначений делегата, использующих `AddressOf`, `Handles`, или `AddHandler`.  
  
 В следующем примере функции `f1`, `f2`, `f3`, и `f4` могут быть назначены `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 Следующий пример доступен, только если `Option Strict` равно `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Игнорирование возвращаемого значения функции  
 Неявное преобразование делегата позволяет назначить функцию `Sub` делегатом, фактически независимо от возвращаемого значения функции. Тем не менее, нельзя назначить `Sub` делегату функции. В следующем примере адрес функции `doubler` назначается `Sub` делегировать `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
