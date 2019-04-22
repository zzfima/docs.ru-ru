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
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838855"
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
