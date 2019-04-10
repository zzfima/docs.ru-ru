---
title: Практическое руководство. Создать лямбда-выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344550"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Практическое руководство. Создать лямбда-выражения (Visual Basic)
Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени. Лямбда-выражение может использоваться везде, где допустим тип делегата.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Чтобы создать функцию однострочное лямбда-выражения  
  
1. В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:  
  
     `Dim add1 =`   `Function`  
  
2. В скобках сразу после `Function`, введите параметры функции. Обратите внимание на то, что не нужно указывать имя после `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. Список параметров введите одно выражение в теле функции. Выражение, результатом которого является значение является значением, возвращаемым функцией. Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Лямбда-выражение вызывается путем передачи в целочисленный аргумент.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. Кроме того в следующем примере выполняется тот же результат:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Создание подпрограммы однострочное лямбда-выражения  
  
1. В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2. В скобках сразу после `Sub`, введите параметры подпрограммы. Обратите внимание на то, что не нужно указывать имя после `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. Список параметров введите одной инструкции в теле подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Лямбда-выражение вызывается путем передачи аргумента строки.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Для создания многострочных лямбда-выражение функции  
  
1. В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2. В скобках сразу после `Function`, введите параметры функции. Обратите внимание на то, что не нужно указывать имя после `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Нажмите клавишу ВВОД. `End Function` Автоматически добавляется инструкция.  
  
4. В теле функции добавьте следующий код, чтобы создать выражение и возвращают значение. Вы не используете `As` предложение, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Лямбда-выражение вызывается путем передачи в целочисленный аргумент.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Создание выражения подпрограммы многострочного лямбда-выражения  
  
1. В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:  
  
     `Dim add1 =`   `Sub`  
  
2. В скобках сразу после `Sub`, введите параметры подпрограммы. Обратите внимание на то, что не нужно указывать имя после `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Нажмите клавишу ВВОД. `End Sub` Автоматически добавляется инструкция.  
  
4. В теле функции добавьте следующий код для выполнения при вызове подпрограммы.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Лямбда-выражение вызывается путем передачи аргумента строки.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Пример  
 Обычно лямбда-выражений используется для определения функции, который может передаваться в качестве аргумента для параметра, тип которого является `Delegate`. В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A> метод возвращает массив процессов, запущенных на локальном компьютере. <xref:System.Linq.Enumerable.Where%2A> Метода из <xref:System.Linq.Enumerable> классу `Boolean` делегат в качестве аргумента. Лямбда-выражение в примере используется для этой цели. Он возвращает `True` каждого процесса, у которой есть только один поток, а те, выбранные в `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 Предыдущий пример эквивалентен следующий код, написанный на [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] синтаксис:  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.Enumerable>
- [Лямбда-выражения](./lambda-expressions.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
