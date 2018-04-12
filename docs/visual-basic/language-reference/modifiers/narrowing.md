---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50116c6212e919d4b9b35fc933d80dee14bd4ecf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Указывает, что оператор преобразования (`CType`) преобразует класс или структуру к типу, который не может содержать некоторые возможные значения исходного класса или структуры.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Преобразования с сужением ключевое слово  
 Процедуры преобразования необходимо указать `Public Shared` в дополнение к `Narrowing`.  
  
 Сужающие преобразования не всегда успешны во время выполнения и может завершиться ошибкой или приводят к потере данных. Примерами являются `Long` для `Integer`, `String` для `Date`и базового типа в производный тип. Это последнее преобразование является сужающим, поскольку базовый тип не может содержать всех членов производного типа и таким образом не является экземпляром производного типа.  
  
 Если `Option Strict` — `On`, необходимо использовать код `CType` для всех сужающих преобразований.  
  
 `Narrowing` Ключевое слово может использоваться в этом контексте:  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
