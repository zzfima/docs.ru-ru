---
title: 'Оператор ?: (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980626"
---
# <a name="-operator-c-reference"></a>Оператор ?: (справочник по C#)

Условный оператор (`?:`), известный как тернарный условный оператор, возвращает одно из двух значений в зависимости от значения логического выражения. Для условного оператора используется следующий синтаксис.  

```csharp
condition ? first_expression : second_expression;  
```

Начиная с C# версии 7.2, выражения `first_expression` и `second_expression` могут быть [`ref`выражениями](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md) с.

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

Результат может быть присвоен переменной с `ref` или `ref readonly`, или переменной без модификатора.

## <a name="remarks"></a>Примечания

Параметр `condition` должен иметь значение `true` или `false`. Если параметр `condition` имеет значение `true`, вычисляется выражение `first_expression` и итог этого вычисления становится результатом. Если параметр `condition` имеет значение `false`, вычисляется выражение `second_expression` и итог этого вычисления становится результатом. В любом случае вычисляется только одно из двух выражений. Это особенно важно для выражений, в которых результат с модификатором `ref`, так как следующий код является допустимым.

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

Ссылка на `storage` не вычисляется, если `storage` имеет значение NULL.

Когда результат представляет собой значение, параметры `first_expression` и `second_expression` должны быть одинакового типа или должно существовать неявное преобразование из одного типа в другой. Если результат с `ref`, параметры `first_expression` и `second_expression` должны быть одинакового типа.

Расчеты, которые в другом случае требовали бы уточнения конструкции `if-else`, можно выражать с помощью условного оператора. Например, в следующем коде сначала используется оператор `if`, а затем — условный оператор для классификации целого числа как положительного или отрицательного.

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

Условный оператор имеет правую ассоциативность. Выражение `a ? b : c ? d : e` вычисляется как `a ? b : (c ? d : e)`, а не как `(a ? b : c) ? d : e`.  
  
Условный оператор не может быть перегружен.
  
## <a name="example"></a>Пример

Ниже приведен пример условного оператора, когда результат является значением.

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

А в следующем примере условного оператора результат является ссылкой.

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [Операторы ?. и ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [?? Оператор](../../../csharp/language-reference/operators/null-coalescing-operator.md)
