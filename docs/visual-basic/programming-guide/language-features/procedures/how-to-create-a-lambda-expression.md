---
title: Практическое руководство. Создание лямбда-выражения
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 1c65841e4c124252cfa41bcd4d0c305a426687ee
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632354"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Практическое руководство. Создание лямбда-выражения (Visual Basic)
*Лямбда-выражение* — это функция или подпрограммы, у которой нет имени. Лямбда-выражение может использоваться везде, где допустим тип делегата.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Создание однострочной функции лямбда-выражения  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:  
  
     `Dim add1 =`   `Function`  
  
2. В скобках сразу после `Function`введите параметры функции. Обратите внимание, что имя не указывается после `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. После списка параметров введите одно выражение в качестве текста функции. Значение, которое вычисляется выражением, — это значение, возвращаемое функцией. Не используйте предложение `As`, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Лямбда-выражение вызывается путем передачи целочисленного аргумента.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. Кроме того, тот же результат достигается в следующем примере:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Создание однострочной подпрограммы лямбда-выражения  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2. В скобках сразу после `Sub`введите параметры подпрограммы. Обратите внимание, что имя не указывается после `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. После списка параметров введите один оператор в качестве текста подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Лямбда-выражение вызывается путем передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Создание многострочной функции лямбда-выражения  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2. В скобках сразу после `Function`введите параметры функции. Обратите внимание, что имя не указывается после `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Нажмите клавишу ВВОД. Инструкция `End Function` добавляется автоматически.  
  
4. В теле функции добавьте следующий код, чтобы создать выражение и вернуть значение. Не используйте предложение `As`, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Лямбда-выражение вызывается путем передачи целочисленного аргумента.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Создание многострочной подпрограммы лямбда-выражений  
  
1. В любой ситуации, где можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:  
  
     `Dim add1 =`   `Sub`  
  
2. В скобках сразу после `Sub`введите параметры подпрограммы. Обратите внимание, что имя не указывается после `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Нажмите клавишу ВВОД. Инструкция `End Sub` добавляется автоматически.  
  
4. В теле функции добавьте следующий код для выполнения при вызове подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Лямбда-выражение вызывается путем передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Пример  
 Обычно лямбда-выражения используются для определения функции, которую можно передать в качестве аргумента для параметра, тип которого `Delegate`. В следующем примере метод <xref:System.Diagnostics.Process.GetProcesses%2A> возвращает массив процессов, запущенных на локальном компьютере. Для метода <xref:System.Linq.Enumerable.Where%2A> из класса <xref:System.Linq.Enumerable> требуется `Boolean` делегат в качестве аргумента. Лямбда-выражение в примере используется для этой цели. Он возвращает `True` для каждого процесса, который имеет только один поток, и выбранные в `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 Предыдущий пример эквивалентен следующему коду, написанному на языке LINQ:  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>См. также:

- <xref:System.Linq.Enumerable>
- [Лямбда-выражения](./lambda-expressions.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)
- [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
