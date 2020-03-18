---
title: Справочник по C#. Ключевое слово class
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 500160d3bc9280b866e5f5ba24c5edc623e752c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673099"
---
# <a name="class-c-reference"></a><span data-ttu-id="91359-102">класс (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="91359-102">class (C# Reference)</span></span>

<span data-ttu-id="91359-103">Классы объявляются с помощью ключевого слова `class`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="91359-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="91359-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="91359-104">Remarks</span></span>

<span data-ttu-id="91359-105">В C# допускается только одиночное наследование.</span><span class="sxs-lookup"><span data-stu-id="91359-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="91359-106">Другими словами, класс может наследовать реализацию только от одного базового класса.</span><span class="sxs-lookup"><span data-stu-id="91359-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="91359-107">Однако класс может реализовывать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="91359-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="91359-108">В таблице ниже приведены примеры наследования класса и реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="91359-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="91359-109">Наследование</span><span class="sxs-lookup"><span data-stu-id="91359-109">Inheritance</span></span>|<span data-ttu-id="91359-110">Пример</span><span class="sxs-lookup"><span data-stu-id="91359-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="91359-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="91359-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="91359-112">Single</span><span class="sxs-lookup"><span data-stu-id="91359-112">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="91359-113">Отсутствует, реализует два интерфейса</span><span class="sxs-lookup"><span data-stu-id="91359-113">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="91359-114">Одиночное, реализует один интерфейс</span><span class="sxs-lookup"><span data-stu-id="91359-114">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="91359-115">Классы, объявленные непосредственно в пространстве имен и не вложенные в другие классы, могут быть [открытыми](./public.md) или [внутренними](./internal.md).</span><span class="sxs-lookup"><span data-stu-id="91359-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="91359-116">По умолчанию классы являются `internal`.</span><span class="sxs-lookup"><span data-stu-id="91359-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="91359-117">Члены класса, включая вложенные классы, могут объявляться с типом доступа [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md) или [private protected](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="91359-117">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="91359-118">По умолчанию члены имеют тип доступа `private`.</span><span class="sxs-lookup"><span data-stu-id="91359-118">Members are `private` by default.</span></span>

<span data-ttu-id="91359-119">Дополнительные сведения см. в статье [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="91359-119">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="91359-120">Можно объявить универсальные классы, имеющие параметры типа.</span><span class="sxs-lookup"><span data-stu-id="91359-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="91359-121">Дополнительные сведения см. в разделе [Универсальные классы](../../programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="91359-121">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="91359-122">Класс может содержать объявления следующих членов:</span><span class="sxs-lookup"><span data-stu-id="91359-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="91359-123">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="91359-123">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="91359-124">Константы</span><span class="sxs-lookup"><span data-stu-id="91359-124">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="91359-125">Поля</span><span class="sxs-lookup"><span data-stu-id="91359-125">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="91359-126">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="91359-126">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="91359-127">Методы</span><span class="sxs-lookup"><span data-stu-id="91359-127">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="91359-128">Свойства</span><span class="sxs-lookup"><span data-stu-id="91359-128">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="91359-129">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="91359-129">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="91359-130">Инструкции</span><span class="sxs-lookup"><span data-stu-id="91359-130">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="91359-131">События</span><span class="sxs-lookup"><span data-stu-id="91359-131">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="91359-132">Делегаты</span><span class="sxs-lookup"><span data-stu-id="91359-132">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="91359-133">Классы</span><span class="sxs-lookup"><span data-stu-id="91359-133">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="91359-134">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="91359-134">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="91359-135">Типы структур</span><span class="sxs-lookup"><span data-stu-id="91359-135">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="91359-136">Типы перечислений</span><span class="sxs-lookup"><span data-stu-id="91359-136">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="91359-137">Пример</span><span class="sxs-lookup"><span data-stu-id="91359-137">Example</span></span>

<span data-ttu-id="91359-138">В приведенном ниже примере показано объявление полей, конструкторов и методов класса.</span><span class="sxs-lookup"><span data-stu-id="91359-138">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="91359-139">В нем также демонстрируется создание экземпляра объекта и печать данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="91359-139">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="91359-140">В этом примере объявляются два класса.</span><span class="sxs-lookup"><span data-stu-id="91359-140">In this example, two classes are declared.</span></span> <span data-ttu-id="91359-141">Первый класс, `Child`, содержит два частных поля (`name` и `age`), два общих конструктора и один общий метод.</span><span class="sxs-lookup"><span data-stu-id="91359-141">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="91359-142">Второй класс, `StringTest`, используется для хранения `Main`.</span><span class="sxs-lookup"><span data-stu-id="91359-142">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="91359-143">Комментарии</span><span class="sxs-lookup"><span data-stu-id="91359-143">Comments</span></span>

<span data-ttu-id="91359-144">Обратите внимание, что в предыдущем примере доступ к частным полям (`name` и `age`) возможен только с помощью общих методов класса `Child`.</span><span class="sxs-lookup"><span data-stu-id="91359-144">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="91359-145">Например, имя ребенка нельзя напечатать из метода `Main` с помощью следующего оператора:</span><span class="sxs-lookup"><span data-stu-id="91359-145">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="91359-146">Получить доступ к закрытым членам класса `Child` из метода `Main` можно было бы лишь в том случае, если бы `Main` был членом класса.</span><span class="sxs-lookup"><span data-stu-id="91359-146">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="91359-147">Типы, объявленные в классе без модификатора доступа, по умолчанию являются `private`, поэтому члены данных в этом примере останутся `private`, если ключевые слова будут удалены.</span><span class="sxs-lookup"><span data-stu-id="91359-147">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="91359-148">Наконец, обратите внимание, что для объекта, созданного с помощью конструктора без параметров (`child3`), поле `age` по умолчанию инициализировано с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="91359-148">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="91359-149">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="91359-149">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="91359-150">См. также</span><span class="sxs-lookup"><span data-stu-id="91359-150">See also</span></span>

- [<span data-ttu-id="91359-151">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="91359-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="91359-152">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="91359-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="91359-153">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="91359-153">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="91359-154">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="91359-154">Reference Types</span></span>](./reference-types.md)
