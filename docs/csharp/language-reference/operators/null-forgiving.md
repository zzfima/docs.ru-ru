---
title: '! — оператор (допускающий значение NULL) — справочник по C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 865e55a28e2f3db85d50a81f6ab29c354ee3c62a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319096"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="5e29a-103">!</span><span class="sxs-lookup"><span data-stu-id="5e29a-103">!</span></span> <span data-ttu-id="5e29a-104">— оператор (допускающий значение NULL) (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5e29a-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="5e29a-105">Унарный постфиксный оператор `!`, доступный в C# 8.0 и более поздних версиях, допускает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="5e29a-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="5e29a-106">При включенном [контексте аннотаций, допускающем значение NULL](../../nullable-references.md#nullable-annotation-context) вы используете оператор, опускающий NULL, для объявления того, что выражение `x` для ссылочного типа, допускающего значение NULL, не равно нулю: `x!`.</span><span class="sxs-lookup"><span data-stu-id="5e29a-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't null: `x!`.</span></span> <span data-ttu-id="5e29a-107">Унарный префиксный оператор `!` является [оператором логического отрицания](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="5e29a-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="5e29a-108">Оператор, допускающий NULL, ни на что не влияет во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5e29a-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="5e29a-109">Он влияет только на статический анализ потока компилятора путем изменения состояния NULL выражения.</span><span class="sxs-lookup"><span data-stu-id="5e29a-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="5e29a-110">Во время выполнения выражение `x!` сравнивается с результатом базового выражения `x`.</span><span class="sxs-lookup"><span data-stu-id="5e29a-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="5e29a-111">Дополнительные сведения о ссылочных типах, допускающих значения NULL, см. в разделе [Ссылочные типы, допускающие значение NULL](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="5e29a-111">For more information about the nullable reference types feature, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="examples"></a><span data-ttu-id="5e29a-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="5e29a-112">Examples</span></span>

<span data-ttu-id="5e29a-113">Один из вариантов использования оператора, допускающего значение NULL, — тестирование логики проверки аргументов.</span><span class="sxs-lookup"><span data-stu-id="5e29a-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="5e29a-114">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="5e29a-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="5e29a-115">С помощью [платформы тестирования MSTest](../../../core/testing/unit-testing-with-mstest.md) можно создать следующий тест для логики проверки в конструкторе:</span><span class="sxs-lookup"><span data-stu-id="5e29a-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="5e29a-116">Без оператора, допускающего значение NULL, компилятор создает следующее предупреждение для предыдущего кода: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="5e29a-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="5e29a-117">Используя оператор, допускающий значение NULL, вы позволяете компилятору узнать, что передача `null` ожидается, и о ней не нужно предупреждать.</span><span class="sxs-lookup"><span data-stu-id="5e29a-117">With the use of the null-forgiving operator, you let the compiler know that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="5e29a-118">Можно также использовать оператор, допускающий значение NULL, если вы точно знаете, что выражение не может быть `null`, но компилятор не распознает это.</span><span class="sxs-lookup"><span data-stu-id="5e29a-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="5e29a-119">В следующем примере, если метод `IsValid` возвращает `true`, его аргумент не является `null`, и вы можете безопасно отменить его ссылку:</span><span class="sxs-lookup"><span data-stu-id="5e29a-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="5e29a-120">Без оператора, допускающего значение NULL, компилятор создает следующее предупреждение для кода `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="5e29a-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="5e29a-121">Если вы можете изменить метод `IsValid`, можно использовать атрибут [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute), чтобы сообщить компилятору, что аргумент метода `IsValid` не может быть `null`, когда метод возвращает `true`:</span><span class="sxs-lookup"><span data-stu-id="5e29a-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to let the compiler know that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="5e29a-122">В предыдущем примере не нужно использовать оператор, допускающий значение NULL, поскольку компилятор содержит достаточно информации, чтобы определить, что `p` не может быть `null` внутри `if`.</span><span class="sxs-lookup"><span data-stu-id="5e29a-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="5e29a-123">Дополнительные сведения об атрибутах, позволяющих указать дополнительные сведения о состоянии NULL для переменной, см. в разделе [Дополнение API атрибутами для определения ожидаемых значений NULL](../../nullable-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="5e29a-123">For more information about the attributes that allow you to specify additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5e29a-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5e29a-124">C# language specification</span></span>

<span data-ttu-id="5e29a-125">См. сведения об [операторе, допускающем значение NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator), в [черновике спецификации по ссылочным типам допускающим значение NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="5e29a-125">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e29a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5e29a-126">See also</span></span>

- [<span data-ttu-id="5e29a-127">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5e29a-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5e29a-128">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="5e29a-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="5e29a-129">Учебник. Разработка с использованием ссылочных типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="5e29a-129">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
