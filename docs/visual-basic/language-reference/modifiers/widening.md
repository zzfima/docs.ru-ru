---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 3b9d1ec15c6c2000fb0842abe25848f853cdf986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703718"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Указывает, что оператор преобразования (`CType`) преобразует класс или структуру к типу, который может содержать все возможные значения исходного класса или структуры.  
  
## <a name="converting-with-the-widening-keyword"></a>С помощью ключевого слова расширяющее преобразование  
 Процедуры преобразования необходимо указать `Public Shared` в дополнение к `Widening`.  
  
 Расширяющие преобразования всегда успешно обрабатываются во время выполнения и никогда не приводят к потере данных. Примерами являются `Single` для `Double`, `Char` для `String`и производный тип к его базовому типу. Последнее преобразование является расширяющим, так как производный тип содержит все члены базового типа и таким образом — это экземпляр базового типа.  
  
 Не использовать код-потребитель `CType` для расширяющих преобразований, даже если `Option Strict` является `On`.  
  
 `Widening` Слово может использоваться в этом контексте:  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Пример определения расширяющие и сужающие преобразования операторов, см. в разделе [как: Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>См. также
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
