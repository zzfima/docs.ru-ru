---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: bd88c05f16a2027b0367effebef809cb5e5abfe8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617441"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Указывает, что оператор преобразования (`CType`) преобразует класс или структуру к типу, который не может содержать некоторые возможные значения исходного класса или структуры.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Преобразования с сужением ключевым словом  
 Процедуры преобразования необходимо указать `Public Shared` в дополнение к `Narrowing`.  
  
 Сужающие преобразования не всегда успешного выполнения во время выполнения и может завершиться ошибкой или приводят к потере данных. Примерами являются `Long` для `Integer`, `String` для `Date`и базового типа к производному типу. Последнее преобразование является сужающим, поскольку базовый тип не может содержать все члены производного типа и таким образом не является экземпляром производного типа.  
  
 Если `Option Strict` — `On`, коду-потребителю необходимо использовать `CType` для всех сужающих преобразований.  
  
 `Narrowing` Слово может использоваться в этом контексте:  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>См. также
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
