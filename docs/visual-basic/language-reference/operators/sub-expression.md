---
title: Часть выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5e8c66f4f2b21a890b8c61e6fc642ce276df6f60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966727"
---
# <a name="sub-expression-visual-basic"></a>Часть выражения (Visual Basic)
Объявляет параметры и код, которые определяют подпрограммы лямбда-выражение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`parameterlist`|Необязательный параметр. Список имен локальных переменных, которые представляют параметры процедуры. Круглые скобки должен присутствовать даже в том случае, если список пуст. Дополнительные сведения см. в разделе [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Обязательный. Один оператор.|  
|`statements`|Обязательный. Список инструкций.|  
  
## <a name="remarks"></a>Примечания  
 Объект *лямбда-выражение* подпрограмма, не имеет имени и которое выполняется одной или нескольких инструкций. Лямбда-выражение можно использовать в любом можно использовать тип делегата, кроме как аргумент `RemoveHandler`. Дополнительные сведения о делегатах и использование лямбда-выражений с делегатами, см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражение напоминает стандартные подпрограммы. Ниже приведены различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражение не может иметь модификатор, такой как `Overloads` или `Overrides`.  
  
-   Тело однострочное лямбда-выражения должно быть инструкцию, а не как выражение. Текст может состоять из вызова процедуры sub, но не вызов процедуры function.  
  
-   Лямбда-выражение все параметры должны указанный типов данных или все параметры должны быть получены.  
  
-   Необязательный и `ParamArray` параметров в лямбда-выражения не разрешены.  
  
-   Универсальные параметры не допускаются в лямбда-выражения.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример лямбда-выражения, который записывает значение в консоль. В примере синтаксиса однострочный и многострочный лямбда-выражения для подпрограммы. Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>См. также
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
- [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
