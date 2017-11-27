---
title: Widening (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 034099397c1d296a42712b8c202e2ac99a0fb43b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Указывает, что оператор преобразования (`CType`) преобразует класс или структуру к типу, который может содержать все возможные значения исходного класса или структуры.  
  
## <a name="converting-with-the-widening-keyword"></a>Преобразование с помощью ключевого слова Widening  
 Процедуры преобразования необходимо указать `Public Shared` в дополнение к `Widening`.  
  
 Расширяющие преобразования всегда выполняться успешно во время выполнения и никогда не приводят к потере данных. Примерами являются `Single` для `Double`, `Char` для `String`и производный тип к его базовому типу. Это последнее преобразование является расширяющим, так как производный тип содержит все члены базового типа и поэтому является экземпляром базового типа.  
  
 Не используйте код-потребитель `CType` для расширяющие преобразования, даже если `Option Strict` — `On`.  
  
 `Widening` Ключевое слово может использоваться в этом контексте:  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Примеры определения расширяющие и сужающие преобразования операторы, в разделе [как: определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
