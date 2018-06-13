---
title: Перечисления в C#. Краткий обзор языка C#
description: Узнайте больше о перечислениях — дискретных именованных константах в C#
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 7fe2626381cb90e55842e3be17dd450eb73d5a5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353358"
---
# <a name="enums"></a><span data-ttu-id="ff8d9-103">перечислениям;</span><span class="sxs-lookup"><span data-stu-id="ff8d9-103">Enums</span></span>

<span data-ttu-id="ff8d9-104">***Тип enum*** представляет собой тип значения с набором именованных констант.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-104">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="ff8d9-105">Перечисления удобно использовать в том случае, когда переменная может иметь только дискретные значения из определенного набора.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-105">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="ff8d9-106">В качестве базового хранилища в перечислении используется один из целочисленных типов значений.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-106">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="ff8d9-107">Перечисления предоставляют семантическое значение для дискретных значений.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-107">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="ff8d9-108">Следующий пример кода объявляет и использует тип `enum` с именем `Color`, в котором определены три константы: `Red`, `Green`, и `Blue`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-108">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="ff8d9-109">Каждый тип `enum` соотносится с одними из целочисленных типов, который является ***базовым типом*** для этого типа `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-109">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="ff8d9-110">Если для типа `enum` базовый тип не объявлен явным образом, ему присваивается базовый тип `int`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-110">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="ff8d9-111">Формат хранения и диапазон возможных значений для типа `enum` определяются его базовым типом.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-111">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="ff8d9-112">Набор значений, которые может принимать `enum`, не ограничивается его членами `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-112">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="ff8d9-113">В частности, любое значение базового типа `enum` можно привести к типу `enum`, и оно будет являться допустимым дискретным значением для этого типа `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-113">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="ff8d9-114">Следующий пример кода объявляет тип `enum` с именем `Alignment` и базовым типом `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-114">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="ff8d9-115">Как показано в предыдущем примере, объявление члена `enum` может содержать константное выражение, задающее значение этого члена.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-115">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="ff8d9-116">Константное значение для каждого члена `enum` должно находиться в диапазоне, определенном для базового типа `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-116">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="ff8d9-117">Когда объявление члена `enum` не указывает значение явным образом, этому члену присваивается нулевое значение (если это первый элемент в типе `enum`) или значение, на единицу превышающее значение последнего объявленного члена `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-117">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="ff8d9-118">Значения `Enum` можно преобразовать к целочисленным значениям, и наоборот, используя приведение типов.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-118">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="ff8d9-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="ff8d9-119">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="ff8d9-120">Для любого типа `enum` по умолчанию устанавливается целочисленное нулевое значение, преобразованное к типу `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-120">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="ff8d9-121">В тех случаях, когда переменная автоматически инициализируются значением по умолчанию, переменным типов `enum` присваивается именно это значение.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-121">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="ff8d9-122">Чтобы значение по умолчанию было легко доступно для любого типа `enum`, литеральное значение `0` неявным образом преобразуется к любому типу `enum`.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-122">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="ff8d9-123">Таким образом, допустимо следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="ff8d9-123">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
<span data-ttu-id="ff8d9-124">[Назад](interfaces.md)
[Вперед](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="ff8d9-124">[Previous](interfaces.md)
[Next](delegates.md)</span></span>
