---
title: Narrowing
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
ms.openlocfilehash: b252f7939e812f31103d4bd98ffd50953679f042
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351480"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Указывает, что оператор преобразования (`CType`) преобразует класс или структуру в тип, который не может содержать некоторые из возможных значений исходного класса или структуры.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Преобразование с помощью ключевого слова "Narrow"  
 В дополнение к `Narrowing`у в процедуре преобразования необходимо указать `Public Shared`.  
  
 Сужающие преобразования не всегда выполняются успешно во время выполнения и могут привести к сбою или потери данных. Примеры `Long` для `Integer`, `String` `Date`и базового типа в производный тип. Последнее преобразование является сужением, так как базовый тип может не содержать все члены производного типа и поэтому не является экземпляром производного типа.  
  
 Если `Option Strict` `On`, то для всех сужающих преобразований код должен использовать `CType`.  
  
 В этом контексте можно использовать ключевое слово `Narrowing`:  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>См. также

- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
