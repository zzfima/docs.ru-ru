---
title: Справочник по C#. Оператор delegate
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 9a78faaccffa9e7d4bf2829d8dfa0fa62a788bba
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039041"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="b4e08-102">Справочник по C#. Оператор delegate</span><span class="sxs-lookup"><span data-stu-id="b4e08-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="b4e08-103">Оператор `delegate` создает анонимный метод, который можно преобразовать в тип делегата:</span><span class="sxs-lookup"><span data-stu-id="b4e08-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="b4e08-104">Начиная с C# 3, лямбда-выражения позволяют быстрее и проще создавать анонимные функции.</span><span class="sxs-lookup"><span data-stu-id="b4e08-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="b4e08-105">С помощью [оператора =>](lambda-operator.md) создайте лямбда-выражение:</span><span class="sxs-lookup"><span data-stu-id="b4e08-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="b4e08-106">См. подробнее о возможностях [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) (например, об использовании внешних переменных).</span><span class="sxs-lookup"><span data-stu-id="b4e08-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="b4e08-107">При использовании оператора `delegate` вам, возможно, нужно будет пропустить список параметров.</span><span class="sxs-lookup"><span data-stu-id="b4e08-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="b4e08-108">В таком случае созданный анонимный метод можно будет преобразовать в тип делегата с любым списком параметров, как показано в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="b4e08-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="b4e08-109">Это единственная функция анонимных методов, которая не поддерживается лямбда-выражениями.</span><span class="sxs-lookup"><span data-stu-id="b4e08-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="b4e08-110">Во всех остальных случаях лямбда-выражение является предпочтительным способом написания встроенного кода.</span><span class="sxs-lookup"><span data-stu-id="b4e08-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="b4e08-111">Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="b4e08-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b4e08-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b4e08-112">C# language specification</span></span>

<span data-ttu-id="b4e08-113">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b4e08-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4e08-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b4e08-114">See also</span></span>

- [<span data-ttu-id="b4e08-115">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b4e08-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b4e08-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b4e08-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="b4e08-117">=> оператор</span><span class="sxs-lookup"><span data-stu-id="b4e08-117">=> operator</span></span>](lambda-operator.md)
