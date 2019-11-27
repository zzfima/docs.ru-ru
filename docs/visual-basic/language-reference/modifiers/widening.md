---
title: Widening
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
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347833"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Указывает, что оператор преобразования (`CType`) преобразует класс или структуру в тип, который может содержать все возможные значения исходного класса или структуры.  
  
## <a name="converting-with-the-widening-keyword"></a>Преобразование с помощью ключевого слова Widening  
 В дополнение к `Widening`у в процедуре преобразования необходимо указать `Public Shared`.  
  
 Расширяющие преобразования всегда выполняются в период выполнения и никогда не вызывают потери данных. Примеры `Single` для `Double`, `Char` `String`и производного типа к его базовому типу. Последнее преобразование является расширяющим, так как производный тип содержит все члены базового типа и, таким же, является экземпляром базового типа.  
  
 В таком коде не обязательно использовать `CType` для расширяющего преобразования, даже если `Option Strict` `On`.  
  
 В этом контексте можно использовать ключевое слово `Widening`:  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Примеры определений расширяющих и суженных операторов преобразования см. в разделе [руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>См. также

- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
