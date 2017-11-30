---
title: "Часть выражения (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sub-expression-visual-basic"></a>Часть выражения (Visual Basic)
Объявляет параметры и код, определяющий подпрограммы лямбда-выражения.  
  
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
|`parameterlist`|Необязательно. Список имен локальных переменных, представляющих параметры этой процедуры. Круглые скобки должны присутствовать даже в том случае, если список пуст. Дополнительные сведения см. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Обязательный. Один оператор.|  
|`statements`|Обязательный. Список инструкций.|  
  
## <a name="remarks"></a>Примечания  
 Объект *лямбда-выражение* представляет собой подпрограмму, которая не имеет имени и которое выполняется один или несколько операторов. Лямбда-выражение можно использовать в любом можно использовать тип делегата, за исключением того, как аргумент `RemoveHandler`. Дополнительные сведения о делегатах и использование лямбда-выражений с делегатами см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражение напоминает, стандартные подпрограммы. Существуют следующие различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражение не может иметь модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Тело Однострочные лямбда-выражения должно быть инструкции, а не к выражению. Текст может состоять из вызова процедуры sub, но не вызов процедуры function.  
  
-   Лямбда-выражение либо все параметры необходимо задать, необходимо определить типы данных или всех параметров.  
  
-   Необязательный и `ParamArray` параметров в лямбда-выражения не допускается.  
  
-   Универсальные параметры в лямбда-выражениях не допускаются.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример лямбда-выражения, записывающего значение на консоль. В примере синтаксиса однострочный и многострочный лямбда-выражения для подпрограммы. Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
