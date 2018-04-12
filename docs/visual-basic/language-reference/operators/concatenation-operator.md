---
title: '&amp;Оператор (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76c8fc52a518dfe7850a5680b7d4f06f3d09bf73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a>&amp;Оператор (Visual Basic)
Создает конкатенацию строк из двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `String` или `Object` переменной.  
  
 `expression1`  
 Обязательный. Любое выражение с типом данных, который расширяется до `String`.  
  
 `expression2`  
 Обязательный. Любое выражение с типом данных, который расширяется до `String`.  
  
## <a name="remarks"></a>Примечания  
 Если тип данных `expression1` или `expression2` не `String` , но может быть расширен до `String`, он преобразуется в `String`. Если любой из типов данных не расширяется до `String`, компилятор создает ошибку.  
  
 Тип данных `result` — `String`. Если один или оба выражения [ничего](../../../visual-basic/language-reference/nothing.md) или иметь значение <xref:System.DBNull.Value?displayProperty=nameWithType>, они рассматриваются как строки со значением «».  
  
> [!NOTE]
>  `&` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Символ амперсанда (&) также может использоваться для определения переменных, как тип `Long`. Дополнительные сведения см. в разделе [символы типа](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `&` оператор для принудительного объединения строк. Результатом является строковое значение, представляющее объединение двух строковых операндов.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы объединения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
