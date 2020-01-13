---
title: Справочник по C#. Модификатор override
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: acad3aa3b196c184132ad1acdf52b18a799b0896
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713252"
---
# <a name="override-c-reference"></a><span data-ttu-id="ff834-102">override (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ff834-102">override (C# Reference)</span></span>

<span data-ttu-id="ff834-103">Модификатор `override` требуется для расширения или изменения абстрактной или виртуальной реализации унаследованного метода, свойства, индексатора или события.</span><span class="sxs-lookup"><span data-stu-id="ff834-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="ff834-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ff834-104">Example</span></span>

<span data-ttu-id="ff834-105">В этом примере класс `Square` должен предоставить переопределенную реализацию `GetArea`, так как `GetArea` является унаследованным от абстрактного класса `Shape`:</span><span class="sxs-lookup"><span data-stu-id="ff834-105">In this example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="ff834-106">Метод `override` предоставляет новую реализацию члена, унаследованного от базового класса.</span><span class="sxs-lookup"><span data-stu-id="ff834-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="ff834-107">Метод, переопределенный объявлением `override`, называется переопределенным базовым методом.</span><span class="sxs-lookup"><span data-stu-id="ff834-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="ff834-108">Переопределенный базовый метод должен иметь ту же сигнатуру, что и метод `override`.</span><span class="sxs-lookup"><span data-stu-id="ff834-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="ff834-109">Дополнительные сведения о наследовании см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="ff834-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="ff834-110">Невиртуальный или статический метод нельзя переопределить.</span><span class="sxs-lookup"><span data-stu-id="ff834-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="ff834-111">Переопределенный базовый метод должен иметь тип `virtual`, `abstract` или `override`.</span><span class="sxs-lookup"><span data-stu-id="ff834-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="ff834-112">Объявление `override` не может изменить доступность метода `virtual`.</span><span class="sxs-lookup"><span data-stu-id="ff834-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="ff834-113">Методы `override` и `virtual` должны иметь одинаковый [модификатор уровня доступа](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ff834-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="ff834-114">Модификаторы `new`, `static` и `virtual` нельзя использовать для изменения метода `override`.</span><span class="sxs-lookup"><span data-stu-id="ff834-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="ff834-115">Переопределяющее объявление свойства должно задавать такие же модификатор уровня доступа, тип и имя, которые имеются у унаследованного свойства, а переопределенное свойство должно иметь тип `virtual`, `abstract` или `override`.</span><span class="sxs-lookup"><span data-stu-id="ff834-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="ff834-116">Дополнительные сведения об использовании ключевого слова `override` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="ff834-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="ff834-117">Пример</span><span class="sxs-lookup"><span data-stu-id="ff834-117">Example</span></span>

<span data-ttu-id="ff834-118">В этом примере определяется базовый класс с именем `Employee` и производный класс с именем `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="ff834-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="ff834-119">Класс `SalesEmployee` включает дополнительное поле `salesbonus`, для использования которого переопределяется метод `CalculatePay`.</span><span class="sxs-lookup"><span data-stu-id="ff834-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="ff834-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ff834-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ff834-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ff834-121">See also</span></span>

- [<span data-ttu-id="ff834-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ff834-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ff834-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff834-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ff834-124">Наследование</span><span class="sxs-lookup"><span data-stu-id="ff834-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="ff834-125">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ff834-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ff834-126">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="ff834-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="ff834-127">abstract</span><span class="sxs-lookup"><span data-stu-id="ff834-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="ff834-128">virtual</span><span class="sxs-lookup"><span data-stu-id="ff834-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="ff834-129">new (модификатор)</span><span class="sxs-lookup"><span data-stu-id="ff834-129">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="ff834-130">Полиморфизм</span><span class="sxs-lookup"><span data-stu-id="ff834-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
