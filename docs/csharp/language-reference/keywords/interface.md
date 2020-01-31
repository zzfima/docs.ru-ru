---
title: interface. Справочник по C#
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: b315d1f04c9e74700afba8ee7871b23ab4b2fd28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744691"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="b7b8a-102">:::no-loc text="interface"::: (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b7b8a-102">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="b7b8a-103">Интерфейс определяет контракт.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-103">An interface defines a contract.</span></span> <span data-ttu-id="b7b8a-104">Любой [`class`](class.md) или [`struct`](struct.md), реализующий этот контракт, должен предоставлять реализацию для членов, определенных в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-104">Any [`class`](class.md) or [`struct`](struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="b7b8a-105">Начиная с C# 8.0, интерфейс может определять реализацию по умолчанию для членов.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-105">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="b7b8a-106">Он также может определять члены [`static`](static.md), чтобы обеспечить единую реализацию для общих функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-106">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="b7b8a-107">В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-107">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="b7b8a-108">Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="b7b8a-108">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="b7b8a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b7b8a-109">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="b7b8a-110">Интерфейс может быть членом пространства имен или класса.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-110">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="b7b8a-111">Объявление интерфейса может содержать объявления (сигнатуры без реализации) следующих членов.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-111">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="b7b8a-112">Методы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-112">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="b7b8a-113">Свойства</span><span class="sxs-lookup"><span data-stu-id="b7b8a-113">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="b7b8a-114">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-114">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="b7b8a-115">События</span><span class="sxs-lookup"><span data-stu-id="b7b8a-115">Events</span></span>](event.md)

<span data-ttu-id="b7b8a-116">Эти предыдущие объявления членов обычно не содержат тело.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-116">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="b7b8a-117">Начиная с C# 8.0, член интерфейса может объявлять тело.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-117">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="b7b8a-118">Этот называется *реализацией по умолчанию*.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-118">This is called a *default implementation*.</span></span> <span data-ttu-id="b7b8a-119">Члены с телом позволяют интерфейсу предоставлять реализацию по умолчанию для классов и структур, которые не предоставляют реализацию с переопределением.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-119">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="b7b8a-120">Кроме того, начиная с C# 8.0, интерфейс может включать следующее.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-120">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="b7b8a-121">Константы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-121">Constants</span></span>](const.md)
- [<span data-ttu-id="b7b8a-122">Инструкции</span><span class="sxs-lookup"><span data-stu-id="b7b8a-122">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="b7b8a-123">[Статический конструктор](../../programming-guide/classes-and-structs/constructors.md#static-constructors)</span><span class="sxs-lookup"><span data-stu-id="b7b8a-123">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="b7b8a-124">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-124">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- [<span data-ttu-id="b7b8a-125">Статические поля, методы, свойства, индексаторы и события</span><span class="sxs-lookup"><span data-stu-id="b7b8a-125">Static fields, methods, properties, indexers, and events</span></span>](static.md)
- <span data-ttu-id="b7b8a-126">Объявления членов с использованием синтаксиса явной реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-126">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="b7b8a-127">Явные модификаторы доступа (доступ по умолчанию — [`public`](access-modifiers.md)).</span><span class="sxs-lookup"><span data-stu-id="b7b8a-127">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="b7b8a-128">Интерфейсы не могут содержать состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-128">Interfaces may not contain instance state.</span></span> <span data-ttu-id="b7b8a-129">Хотя статические поля теперь разрешены, поля экземпляров в интерфейсах запрещены.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-129">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="b7b8a-130">[Автосвойства экземпляра](../../programming-guide/classes-and-structs/auto-implemented-properties.md) не поддерживаются в интерфейсах, так как они неявно объявляют скрытое поле.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-130">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="b7b8a-131">Это правило оказывает незначительное воздействие на объявления свойств.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-131">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="b7b8a-132">В объявлении интерфейса следующий код не объявляет автоматически реализуемое свойство, как в `class` или `struct`.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-132">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="b7b8a-133">Вместо этого он объявляет свойство, которое не имеет реализации по умолчанию, но должно быть реализовано в любом типе, реализующем интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-133">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="b7b8a-134">Интерфейс может наследовать от одного или нескольких базовых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-134">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="b7b8a-135">Когда интерфейс [переопределяет метод](override.md), реализованный в базовом интерфейсе, он должен использовать синтаксис [явной реализации интерфейса](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="b7b8a-135">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="b7b8a-136">Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-136">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="b7b8a-137">Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-137">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="b7b8a-138">При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-138">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="b7b8a-139">Кроме того, обращение к членам интерфейса по умолчанию можно осуществлять только через экземпляр интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-139">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="b7b8a-140">Дополнительные сведения о явной реализации интерфейса см. в статье [Явная реализация интерфейса](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="b7b8a-140">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="b7b8a-141">Пример</span><span class="sxs-lookup"><span data-stu-id="b7b8a-141">Example</span></span>

<span data-ttu-id="b7b8a-142">В следующем примере показана реализация интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-142">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="b7b8a-143">В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-143">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="b7b8a-144">Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="b7b8a-144">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="b7b8a-145">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b7b8a-145">C# language specification</span></span>

<span data-ttu-id="b7b8a-146">Дополнительные сведения см. в разделе [Интерфейсы](~/_csharplang/spec/interfaces.md) статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md), а также в спецификации функций для [элементов интерфейса по умолчанию — C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md).</span><span class="sxs-lookup"><span data-stu-id="b7b8a-146">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="b7b8a-147">См. также</span><span class="sxs-lookup"><span data-stu-id="b7b8a-147">See also</span></span>

- [<span data-ttu-id="b7b8a-148">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b7b8a-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b7b8a-149">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b7b8a-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b7b8a-150">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b7b8a-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b7b8a-151">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-151">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="b7b8a-152">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-152">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="b7b8a-153">Использование свойств</span><span class="sxs-lookup"><span data-stu-id="b7b8a-153">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="b7b8a-154">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="b7b8a-154">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="b7b8a-155">class</span><span class="sxs-lookup"><span data-stu-id="b7b8a-155">class</span></span>](class.md)
- [<span data-ttu-id="b7b8a-156">struct</span><span class="sxs-lookup"><span data-stu-id="b7b8a-156">struct</span></span>](struct.md)
- [<span data-ttu-id="b7b8a-157">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b7b8a-157">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
