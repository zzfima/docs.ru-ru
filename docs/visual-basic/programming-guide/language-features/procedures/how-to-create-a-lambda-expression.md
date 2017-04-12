---
title: "Практическое руководство: создание лямбда-выражения (Visual Basic) | Документы Microsoft"
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
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 5e105e87b1e63218f2c3c2204350257c139b5837
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Практическое руководство. Создание лямбда-выражения (Visual Basic)
Объект *лямбда-выражение* функцию или подпрограмму, которая не имеет имени. Лямбда-выражение можно использовать везде, где допустим тип делегата.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Чтобы создать функцию Однострочные лямбда-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере:  
  
     `Dim add1 =`   `Function`  
  
2.  В скобках непосредственно после `Function`, введите параметры функции. Обратите внимание, что не задано имя после `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Вслед за списком параметров введите одно выражение как тело функции. Значение, выражение, результатом вычисления которого является значение, возвращаемое функцией. Не используйте `As` предложение, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Лямбда-выражение вызывается путем передачи ему целочисленного аргумента.  
  
     [!code-vb[VbVbalrLambdas&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  Кроме того тот же результат достигается в следующем примере:  
  
     [!code-vb[VbVbalrLambdas&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Создание подпрограммы Однострочные лямбда-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере.  
  
     `Dim add1 =`   `Sub`  
  
2.  В скобках непосредственно после `Sub`, введите параметры подпрограммы. Обратите внимание, что не задано имя после `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Вслед за списком параметров введите один оператор как тело подпрограммы.  
  
     [!code-vb[VbVbalrLambdas&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Лямбда-выражение вызывается передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Для создания многострочных лямбда-функцией, выражение  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Function`, как показано в следующем примере.  
  
     `Dim add1 =`   `Function`  
  
2.  В скобках непосредственно после `Function`, введите параметры функции. Обратите внимание, что не задано имя после `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Нажмите клавишу ВВОД. `End Function` Автоматически добавляется инструкция.  
  
4.  В теле функции добавьте следующий код, чтобы создать выражение и вернуть значение. Не используйте `As` предложение, чтобы указать тип возвращаемого значения.  
  
     [!code-vb[VbVbalrLambdas&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Лямбда-выражение вызывается путем передачи ему целочисленного аргумента.  
  
     [!code-vb[VbVbalrLambdas&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Создание выражения подпрограммы многострочных лямбда-выражения  
  
1.  В любой ситуации, когда можно использовать тип делегата, введите ключевое слово `Sub`, как показано в следующем примере:  
  
     `Dim add1 =`   `Sub`  
  
2.  В скобках непосредственно после `Sub`, введите параметры подпрограммы. Обратите внимание, что не задано имя после `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Нажмите клавишу ВВОД. `End Sub` Автоматически добавляется инструкция.  
  
4.  В теле функции добавьте следующий код для выполнения при вызове подпрограммы.  
  
     [!code-vb[VbVbalrLambdas&#21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Лямбда-выражение вызывается передачи строкового аргумента.  
  
     [!code-vb[VbVbalrLambdas&#22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Пример  
 Обычно лямбда-выражений используется для определения функции, который можно передать в качестве аргумента для параметра, тип которого является `Delegate`. В следующем примере <xref:System.Diagnostics.Process.GetProcesses%2A>метод возвращает массив процессов, запущенных на локальном компьютере.</xref:System.Diagnostics.Process.GetProcesses%2A> <xref:System.Linq.Enumerable.Where%2A>Метод <xref:System.Linq.Enumerable>класса требуется `Boolean` делегат в качестве аргумента.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A> Лямбда-выражение в примере используется для этой цели. Он возвращает `True` для каждого процесса, имеет только один поток, а те, выбранные в `filteredList`.  
  
 [!code-vb[VbVbalrLambdas&#10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 Предыдущий пример эквивалентен следующий код, который записывается в [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] синтаксис:  
  
 [!code-vb[VbVbalrLambdas&11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Лямбда-выражения](./lambda-expressions.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Практическое руководство: передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
