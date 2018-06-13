---
title: Практическое руководство. Создание лямбда-выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: f437166bc5206b4145d6508aa2131ec94d6eca95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653550"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Практическое руководство. Создание лямбда-выражения (Visual Basic)
Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени. Лямбда-выражение можно использовать везде, где допустим тип делегата.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Чтобы создать функцию Однострочные лямбда-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:  
  
     `Dim add1 =`   `Function`  
  
2.  В круглых скобках непосредственно после `Function`, введите параметры функции. Обратите внимание, что вы не задавать имя после `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Вслед за списком параметров введите одно выражение как тело функции. Значение, выражение, результатом вычисления которого является значение, возвращаемое функцией. Не используйте `As` предложений, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Лямбда-выражение вызывается путем передачи в целочисленный аргумент.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  Кроме того в следующем примере выполняется тот же результат:  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Создание подпрограммы Однострочные лямбда-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2.  В круглых скобках непосредственно после `Sub`, введите параметры подпрограммы. Обратите внимание, что вы не задавать имя после `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Вслед за списком параметров введите один оператор как тело подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Лямбда-выражение вызывается передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Для создания многострочного лямбда-функцией, выражение  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2.  В круглых скобках непосредственно после `Function`, введите параметры функции. Обратите внимание, что вы не задавать имя после `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Нажмите клавишу ВВОД. `End Function` Автоматически добавляется инструкция.  
  
4.  В теле функции добавьте следующий код для создания выражения и возвращают значение. Не используйте `As` предложений, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Лямбда-выражение вызывается путем передачи в целочисленный аргумент.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Создание выражения подпрограммы многострочного лямбда-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:  
  
     `Dim add1 =`   `Sub`  
  
2.  В круглых скобках непосредственно после `Sub`, введите параметры подпрограммы. Обратите внимание, что вы не задавать имя после `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Нажмите клавишу ВВОД. `End Sub` Автоматически добавляется инструкция.  
  
4.  В теле функции добавьте следующий код для выполнения при вызове подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Лямбда-выражение вызывается передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Пример  
 Обычно лямбда-выражений используется для определения функции, который можно передать в качестве аргумента для параметра, тип которого является `Delegate`. В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A> метод возвращает массив процессов, запущенных на локальном компьютере. <xref:System.Linq.Enumerable.Where%2A> Метод <xref:System.Linq.Enumerable> класс требует `Boolean` делегат в качестве аргумента. Лямбда-выражения в примере используется для этой цели. Он возвращает `True` для каждого процесса, который имеет только один поток, а те, выбранных в `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 Предыдущий пример эквивалентно следующему коду, написанному в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] синтаксис:  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.Enumerable>  
 [Лямбда-выражения](./lambda-expressions.md)  
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)  
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
