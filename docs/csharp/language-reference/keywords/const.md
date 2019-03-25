---
title: Справочник по C#. Ключевое слово const
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 7cf4fc52691565a850b4f34574828ad4e043998e
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307893"
---
# <a name="const-c-reference"></a><span data-ttu-id="ecb15-102">const (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ecb15-102">const (C# Reference)</span></span>

<span data-ttu-id="ecb15-103">Для объявления константного поля или константной локальной используется ключевое слово `const`.</span><span class="sxs-lookup"><span data-stu-id="ecb15-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="ecb15-104">Константные поля и локальные не являются переменными и не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="ecb15-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="ecb15-105">Константы могут быть числами, логическими значениями, строками или нулевыми ссылками.</span><span class="sxs-lookup"><span data-stu-id="ecb15-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="ecb15-106">Не создавайте константу для предоставления сведений, которые могут измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="ecb15-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="ecb15-107">Например, не используйте константное поле для хранения цены услуги, номера версии продукта или торгового названия компании.</span><span class="sxs-lookup"><span data-stu-id="ecb15-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="ecb15-108">Эти значения могут со временем измениться, а поскольку константы распространяются компиляторами, для отражения изменений потребуется повторная компиляция остальных кодов, скомпилированных с использованием ваших библиотек.</span><span class="sxs-lookup"><span data-stu-id="ecb15-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="ecb15-109">См. также описание ключевого слова [readonly](../../../csharp/language-reference/keywords/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ecb15-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="ecb15-110">Например:</span><span class="sxs-lookup"><span data-stu-id="ecb15-110">For example:</span></span>

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="ecb15-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecb15-111">Remarks</span></span>

<span data-ttu-id="ecb15-112">Тип объявления константы указывает на тип членов, которые вводятся объявлением.</span><span class="sxs-lookup"><span data-stu-id="ecb15-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="ecb15-113">Инициализатор локальной константы или константного поля должен быть выражением константы, поддерживающим неявное преобразование в конечный тип.</span><span class="sxs-lookup"><span data-stu-id="ecb15-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="ecb15-114">Выражение константы — это выражение, которое можно полностью вычислить во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="ecb15-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="ecb15-115">Таким образом, единственно возможными значениями для констант типов ссылок являются `string` и нулевые ссылки.</span><span class="sxs-lookup"><span data-stu-id="ecb15-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="ecb15-116">Объявление константы может объявлять несколько констант, например:</span><span class="sxs-lookup"><span data-stu-id="ecb15-116">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

<span data-ttu-id="ecb15-117">Модификатор `static` в объявлении константы не допускается.</span><span class="sxs-lookup"><span data-stu-id="ecb15-117">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="ecb15-118">Константа может участвовать в выражении константы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ecb15-118">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> <span data-ttu-id="ecb15-119">Ключевое слово [readonly](../../../csharp/language-reference/keywords/readonly.md) отличается от ключевого слова `const`.</span><span class="sxs-lookup"><span data-stu-id="ecb15-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="ecb15-120">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="ecb15-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="ecb15-121">Поле `readonly` может быть инициализировано при объявлении или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="ecb15-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="ecb15-122">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="ecb15-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="ecb15-123">Также, несмотря на то, что поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующей строке: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="ecb15-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="ecb15-124">Пример</span><span class="sxs-lookup"><span data-stu-id="ecb15-124">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="ecb15-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ecb15-125">Example</span></span>

<span data-ttu-id="ecb15-126">В этом примере показан способ использования констант в качестве локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="ecb15-126">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="ecb15-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ecb15-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ecb15-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ecb15-128">See also</span></span>

- [<span data-ttu-id="ecb15-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ecb15-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="ecb15-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ecb15-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ecb15-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ecb15-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="ecb15-132">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="ecb15-132">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
- [<span data-ttu-id="ecb15-133">readonly</span><span class="sxs-lookup"><span data-stu-id="ecb15-133">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)
