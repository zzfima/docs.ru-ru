---
title: Неявное преобразование делегата
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345221"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Неявное преобразование делегата (Visual Basic)
Неявное преобразование делегатов позволяет назначать процедуры и функции делегатам или обработчикам, даже если их сигнатуры не идентичны. Таким образом, привязка к делегатам будет соответствовать привязке, уже разрешенной для вызовов методов.  
  
## <a name="parameters-and-return-type"></a>Параметры и возвращаемый тип  
 Вместо точного соответствия сигнатуры для ослабленного преобразования требуется выполнение следующих условий, если `Option Strict` имеет значение `On`.  
  
- Должно существовать расширяющее преобразование из типа данных каждого параметра делегата в тип данных соответствующего параметра назначенной функции или `Sub`. В следующем примере делегат `Del1` имеет один параметр — `Integer`. Параметр `m` в назначенных лямбда-выражениях должен иметь тип данных, для которого существует расширяющее преобразование из `Integer`, например `Long` или `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Сужающие преобразования разрешены, только если `Option Strict` имеет значение `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- Расширяющее преобразование должно существовать в обратном направлении от возвращаемого типа назначенной функции или `Sub` типу возвращаемого значения делегата. В следующих примерах текст каждого назначенного лямбда-выражения должен иметь тип данных, который расширяется на `Integer`, поскольку тип возвращаемого значения `del1` — `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Если `Option Strict` имеет значение `Off`, расширяющееся ограничение удаляется в обоих направлениях.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Пропуск спецификаций параметров  
 Ослабленные делегаты также позволяют полностью опускать спецификации параметров в назначенном методе:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Обратите внимание, что нельзя указать некоторые параметры и опустить другие.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 Возможность опускать параметры полезна в таких ситуациях, как определение обработчика событий, в котором участвуют несколько сложных параметров. Аргументы некоторых обработчиков событий не используются. Вместо этого обработчик напрямую обращается к состоянию элемента управления, в котором регистрируется событие, и игнорирует аргументы. Ослабленные делегаты позволяют опускать аргументы в таких объявлениях, если результат неоднозначности. В следующем примере полностью указанный метод `OnClick` может быть перезаписан как `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Примеры AddressOf  
 Лямбда-выражения используются в предыдущих примерах для упрощения просмотра связей типов. Тем не менее, для назначений делегатов, использующих `AddressOf`, `Handles`или `AddHandler`, разрешены одни и те же ограничения.  
  
 В следующем примере функции `f1`, `f2`, `f3`и `f4` могут быть назначены `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 Следующий пример допустим только в том случае, если `Option Strict` имеет значение `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Удаление возвращаемых функций  
 Неявное преобразование делегата позволяет присвоить функцию делегату `Sub`, фактически игнорируя возвращаемое значение функции. Однако нельзя присвоить `Sub` делегату функции. В следующем примере адрес функции `doubler` назначается `Sub` `Del3`делегата.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>См. также

- [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
