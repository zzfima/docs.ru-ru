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
# <a name="-operator-c-reference"></a><span data-ttu-id="aa6af-102">Оператор ?: (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="aa6af-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="aa6af-103">Условный оператор (`?:`), известный как тернарный условный оператор, возвращает одно из двух значений в зависимости от значения логического выражения.</span><span class="sxs-lookup"><span data-stu-id="aa6af-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="aa6af-104">Для условного оператора используется следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="aa6af-104">Following is the syntax for the conditional operator.</span></span>  

```csharp
condition ? first_expression : second_expression;  
```

<span data-ttu-id="aa6af-105">Начиная с C# версии 7.2, выражения `first_expression` и `second_expression` могут быть [`ref`выражениями](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md) с.</span><span class="sxs-lookup"><span data-stu-id="aa6af-105">Beginning with C# 7.2, the `first_expression` and `second_expression` my be [`ref` expressions](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span></span>

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

<span data-ttu-id="aa6af-106">Результат может быть присвоен переменной с `ref` или `ref readonly`, или переменной без модификатора.</span><span class="sxs-lookup"><span data-stu-id="aa6af-106">The result may be assigned to a `ref` or `ref readonly` variable, or to a variable with neither modifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa6af-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa6af-107">Remarks</span></span>

<span data-ttu-id="aa6af-108">Параметр `condition` должен иметь значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="aa6af-108">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="aa6af-109">Если параметр `condition` имеет значение `true`, вычисляется выражение `first_expression` и итог этого вычисления становится результатом.</span><span class="sxs-lookup"><span data-stu-id="aa6af-109">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="aa6af-110">Если параметр `condition` имеет значение `false`, вычисляется выражение `second_expression` и итог этого вычисления становится результатом.</span><span class="sxs-lookup"><span data-stu-id="aa6af-110">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="aa6af-111">В любом случае вычисляется только одно из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="aa6af-111">Only one of the two expressions is evaluated.</span></span> <span data-ttu-id="aa6af-112">Это особенно важно для выражений, в которых результат с модификатором `ref`, так как следующий код является допустимым.</span><span class="sxs-lookup"><span data-stu-id="aa6af-112">This is particularly important for expressions where the result is a `ref`, as the following is valid:</span></span>

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

<span data-ttu-id="aa6af-113">Ссылка на `storage` не вычисляется, если `storage` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="aa6af-113">The reference to `storage` is not evaluated when `storage` is null.</span></span>

<span data-ttu-id="aa6af-114">Когда результат представляет собой значение, параметры `first_expression` и `second_expression` должны быть одинакового типа или должно существовать неявное преобразование из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="aa6af-114">When the result is a value, the type of `first_expression` and `second_expression` must be the same, or there must be an implicit conversion from one type to the other.</span></span> <span data-ttu-id="aa6af-115">Если результат с `ref`, параметры `first_expression` и `second_expression` должны быть одинакового типа.</span><span class="sxs-lookup"><span data-stu-id="aa6af-115">When the result is a `ref`, the type of `first_expression` and `second_expression` must be the same.</span></span>

<span data-ttu-id="aa6af-116">Расчеты, которые в другом случае требовали бы уточнения конструкции `if-else`, можно выражать с помощью условного оператора.</span><span class="sxs-lookup"><span data-stu-id="aa6af-116">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="aa6af-117">Например, в следующем коде сначала используется оператор `if`, а затем — условный оператор для классификации целого числа как положительного или отрицательного.</span><span class="sxs-lookup"><span data-stu-id="aa6af-117">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>

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

<span data-ttu-id="aa6af-118">Условный оператор имеет правую ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="aa6af-118">The conditional operator is right-associative.</span></span> <span data-ttu-id="aa6af-119">Выражение `a ? b : c ? d : e` вычисляется как `a ? b : (c ? d : e)`, а не как `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="aa6af-119">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
<span data-ttu-id="aa6af-120">Условный оператор не может быть перегружен.</span><span class="sxs-lookup"><span data-stu-id="aa6af-120">The conditional operator cannot be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="aa6af-121">Пример</span><span class="sxs-lookup"><span data-stu-id="aa6af-121">Example</span></span>

<span data-ttu-id="aa6af-122">Ниже приведен пример условного оператора, когда результат является значением.</span><span class="sxs-lookup"><span data-stu-id="aa6af-122">The following example shows the conditional operator whose result is a value:</span></span>

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

<span data-ttu-id="aa6af-123">А в следующем примере условного оператора результат является ссылкой.</span><span class="sxs-lookup"><span data-stu-id="aa6af-123">The following alternative shows the conditional operator where the result is a reference:</span></span>

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a><span data-ttu-id="aa6af-124">См. также</span><span class="sxs-lookup"><span data-stu-id="aa6af-124">See Also</span></span>

- [<span data-ttu-id="aa6af-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="aa6af-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="aa6af-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="aa6af-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="aa6af-127">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="aa6af-127">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="aa6af-128">if-else</span><span class="sxs-lookup"><span data-stu-id="aa6af-128">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="aa6af-129">[Операторы ?. и ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="aa6af-129">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="aa6af-130">?? Оператор</span><span class="sxs-lookup"><span data-stu-id="aa6af-130">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
