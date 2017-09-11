---
title: "Перечисления в C#. Краткий обзор языка C#"
description: "Узнайте больше о перечислениях — дискретных именованных константах в C#"
keywords: .NET, C#
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 77d315dd87d9cab32605de415674d146eb9115fa
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
    
# <a name="enums"></a><span data-ttu-id="5e516-104">Перечисления</span><span class="sxs-lookup"><span data-stu-id="5e516-104">Enums</span></span>

<span data-ttu-id="5e516-105">***Тип enum*** представляет собой тип значения с набором именованных констант.</span><span class="sxs-lookup"><span data-stu-id="5e516-105">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="5e516-106">Перечисления удобно использовать в том случае, когда переменная может иметь только дискретные значения из определенного набора.</span><span class="sxs-lookup"><span data-stu-id="5e516-106">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="5e516-107">В качестве базового хранилища в перечислении используется один из целочисленных типов значений.</span><span class="sxs-lookup"><span data-stu-id="5e516-107">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="5e516-108">Перечисления предоставляют семантическое значение для дискретных значений.</span><span class="sxs-lookup"><span data-stu-id="5e516-108">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="5e516-109">Следующий пример кода объявляет и использует тип `enum` с именем `Color`, в котором определены три константы: `Red`, `Green`, и `Blue`.</span><span class="sxs-lookup"><span data-stu-id="5e516-109">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

<span data-ttu-id="5e516-110">[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]</span><span class="sxs-lookup"><span data-stu-id="5e516-110">[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]</span></span>

<span data-ttu-id="5e516-111">Каждый тип `enum` соотносится с одними из целочисленных типов, который является ***базовым типом*** для этого типа `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-111">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="5e516-112">Если для типа `enum` базовый тип не объявлен явным образом, ему присваивается базовый тип `int`.</span><span class="sxs-lookup"><span data-stu-id="5e516-112">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="5e516-113">Формат хранения и диапазон возможных значений для типа `enum` определяются его базовым типом.</span><span class="sxs-lookup"><span data-stu-id="5e516-113">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="5e516-114">Набор значений, которые может принимать `enum`, не ограничивается его членами `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-114">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="5e516-115">В частности, любое значение базового типа `enum` можно привести к типу `enum`, и оно будет являться допустимым дискретным значением для этого типа `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-115">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="5e516-116">Следующий пример кода объявляет тип `enum` с именем `Alignment` и базовым типом `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="5e516-116">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

<span data-ttu-id="5e516-117">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]</span><span class="sxs-lookup"><span data-stu-id="5e516-117">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]</span></span>

<span data-ttu-id="5e516-118">Как показано в предыдущем примере, объявление члена `enum` может содержать константное выражение, задающее значение этого члена.</span><span class="sxs-lookup"><span data-stu-id="5e516-118">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="5e516-119">Константное значение для каждого члена `enum` должно находиться в диапазоне, определенном для базового типа `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-119">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="5e516-120">Когда объявление члена `enum` не указывает значение явным образом, этому члену присваивается нулевое значение (если это первый элемент в типе `enum`) или значение, на единицу превышающее значение последнего объявленного члена `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-120">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="5e516-121">Значения `Enum` можно преобразовать к целочисленным значениям, и наоборот, используя приведение типов.</span><span class="sxs-lookup"><span data-stu-id="5e516-121">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="5e516-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e516-122">For example:</span></span>

<span data-ttu-id="5e516-123">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]</span><span class="sxs-lookup"><span data-stu-id="5e516-123">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]</span></span>

<span data-ttu-id="5e516-124">Для любого типа `enum` по умолчанию устанавливается целочисленное нулевое значение, преобразованное к типу `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-124">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="5e516-125">В тех случаях, когда переменная автоматически инициализируются значением по умолчанию, переменным типов `enum` присваивается именно это значение.</span><span class="sxs-lookup"><span data-stu-id="5e516-125">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="5e516-126">Чтобы значение по умолчанию было легко доступно для любого типа `enum`, литеральное значение `0` неявным образом преобразуется к любому типу `enum`.</span><span class="sxs-lookup"><span data-stu-id="5e516-126">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="5e516-127">Таким образом, допустимо следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="5e516-127">Thus, the following is permitted.</span></span>

<span data-ttu-id="5e516-128">[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]</span><span class="sxs-lookup"><span data-stu-id="5e516-128">[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5e516-129">[Назад](interfaces.md)
[Вперед](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="5e516-129">[Previous](interfaces.md)
[Next](delegates.md)</span></span>

