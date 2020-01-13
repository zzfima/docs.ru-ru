---
title: Модификатор sealed. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: 686afd5d9d0394bb1a802551b65083732599f384
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713109"
---
# <a name="sealed-c-reference"></a><span data-ttu-id="2cd8f-102">sealed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2cd8f-102">sealed (C# Reference)</span></span>

<span data-ttu-id="2cd8f-103">При применении к классу модификатор `sealed` запрещает другим классам наследовать от этого класса.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="2cd8f-104">В следующем примере класс `B` наследует от класса `A`, но никакие классы не могут наследовать от класса `B`.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>

```csharp
class A {}
sealed class B : A {}
```

<span data-ttu-id="2cd8f-105">Модификатор `sealed` можно использовать для метода или свойства, которое переопределяет виртуальный метод или свойство в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="2cd8f-106">Это позволяет классам наследовать от вашего класса, запрещая им при этом переопределять определенные виртуальные методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>

## <a name="example"></a><span data-ttu-id="2cd8f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2cd8f-107">Example</span></span>

<span data-ttu-id="2cd8f-108">В следующем примере класс `Z` наследует от класса `Y`, но `Z` не может переопределить виртуальную функцию `F`, которая объявлена в классе `X` и запечатана в классе `Y`.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>

[!code-csharp[csrefKeywordsModifiers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#16)]

<span data-ttu-id="2cd8f-109">Чтобы предотвратить переопределение производных классов при определении новых методов или свойств, не назначайте их в качестве виртуальных ([virtual](virtual.md)).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-109">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](virtual.md).</span></span>

<span data-ttu-id="2cd8f-110">Нельзя использовать модификатор [abstract](abstract.md) с запечатанным классом, поскольку абстрактный класс должен наследоваться классом, реализующим абстрактные методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-110">It is an error to use the [abstract](abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>

<span data-ttu-id="2cd8f-111">При применении к методу или свойству модификатор `sealed` всегда следует использовать с [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-111">When applied to a method or property, the `sealed` modifier must always be used with [override](override.md).</span></span>

<span data-ttu-id="2cd8f-112">Поскольку структуры неявно запечатаны, их нельзя наследовать.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-112">Because structs are implicitly sealed, they cannot be inherited.</span></span>

<span data-ttu-id="2cd8f-113">Дополнительные сведения см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-113">For more information, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="2cd8f-114">Дополнительные примеры см. в разделе [Абстрактные и запечатанные классы и члены классов](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-114">For more examples, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="2cd8f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="2cd8f-115">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#17)]

<span data-ttu-id="2cd8f-116">Чтобы наследовать от запечатанного класса, можно применить следующую инструкцию в приведенном выше примере:</span><span class="sxs-lookup"><span data-stu-id="2cd8f-116">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>

`class MyDerivedC: SealedClass {}   // Error`

<span data-ttu-id="2cd8f-117">В результате выдается сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="2cd8f-117">The result is an error message:</span></span>

`'MyDerivedC': cannot derive from sealed type 'SealedClass'`

## <a name="remarks"></a><span data-ttu-id="2cd8f-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="2cd8f-118">Remarks</span></span>

<span data-ttu-id="2cd8f-119">Чтобы определить, нужно ли запечатывать класс, метод или свойство, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="2cd8f-119">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>

- <span data-ttu-id="2cd8f-120">потенциальные преимущества, которые производные классы могут получить от возможности настраивать ваш класс;</span><span class="sxs-lookup"><span data-stu-id="2cd8f-120">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>

- <span data-ttu-id="2cd8f-121">вероятность того, что производные классы могут корректировать ваши классы, препятствуя их нормальной работе.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-121">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2cd8f-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2cd8f-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2cd8f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2cd8f-123">See also</span></span>

- [<span data-ttu-id="2cd8f-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2cd8f-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2cd8f-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2cd8f-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2cd8f-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="2cd8f-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2cd8f-127">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="2cd8f-127">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="2cd8f-128">Абстрактные и запечатанные классы и члены классов</span><span class="sxs-lookup"><span data-stu-id="2cd8f-128">Abstract and Sealed Classes and Class Members</span></span>](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="2cd8f-129">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="2cd8f-129">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="2cd8f-130">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="2cd8f-130">Modifiers</span></span>](index.md)
- [<span data-ttu-id="2cd8f-131">override</span><span class="sxs-lookup"><span data-stu-id="2cd8f-131">override</span></span>](override.md)
- [<span data-ttu-id="2cd8f-132">virtual</span><span class="sxs-lookup"><span data-stu-id="2cd8f-132">virtual</span></span>](virtual.md)
