---
title: as (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 092c30a858df7baeb35bdf28bae53802fb0916d4
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172023"
---
# <a name="as-c-reference"></a>as (Справочник по C#)
Оператор `as` можно использовать для выполнения определенных типов преобразований между совместимыми ссылочными типами или [типами, допускающими значение NULL](../../../csharp/programming-guide/nullable-types/index.md). Вот пример кода:  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>Примечания  
 Оператор `as` аналогичен операции приведения. Однако, если преобразование невозможно, `as` возвращает `null`, а не вызывает исключение. Рассмотрим следующий пример.  
  
```csharp  
expression as type  
```  
  
 Этот код является эквивалентом следующего выражения, за исключением того, что переменная `expression` вычисляется только один раз.  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 Обратите внимание, что оператор `as` выполняет только преобразования ссылок, преобразования типов, допускающих значение NULL, и преобразования-упаковки. Оператор `as` не может выполнять другие преобразования, например пользовательские преобразования, которые следует выполнять с помощью выражения приведения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [Оператор ?:](../../../csharp/language-reference/operators/conditional-operator.md)  
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)
