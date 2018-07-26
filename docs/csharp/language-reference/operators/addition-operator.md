---
title: + Оператор (ссылка C#)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d4a269c07e0d6dc2ac6a6a101f200653c6ea7a29
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244875"
---
# <a name="-operator-c-reference"></a>Оператор + (справочник по C#)
Оператор `+` может функционировать как унарный или как бинарный оператор.  
  
## <a name="remarks"></a>Примечания  
 Унарные операторы `+` предварительно определены для всех числовых типов. Результатом использования унарного оператора `+` для числового типа является просто значение операнда.  
  
 Бинарные операторы `+` предварительно определены для числовых и строковых типов. Для числовых типов оператор "+" вычисляет сумму двух его операндов. Если один или оба операнда имеют строковый тип, оператор "+" сцепляет строковые представления операндов.  
  
 Для типов делегатов также используется бинарный оператор `+`, который выполняет сцепление делегатов.  
  
 Пользовательские типы могут перегружать унарный оператор `+` и бинарный оператор `+`. Операции с целыми типами обычно разрешены и для перечислений. Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)
