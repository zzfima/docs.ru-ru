---
title: класс (Справочник по C#)
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 20968d2f72195db6d16de1b726c6e946b91ffcd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="class-c-reference"></a><span data-ttu-id="cd308-102">класс (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cd308-102">class (C# Reference)</span></span>

<span data-ttu-id="cd308-103">Классы объявляются с помощью ключевого слова `class`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cd308-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates 
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="cd308-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd308-104">Remarks</span></span>
<span data-ttu-id="cd308-105">В C# допускается только одиночное наследование.</span><span class="sxs-lookup"><span data-stu-id="cd308-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="cd308-106">Другими словами, класс может наследовать реализацию только от одного базового класса.</span><span class="sxs-lookup"><span data-stu-id="cd308-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="cd308-107">Однако класс может реализовывать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="cd308-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="cd308-108">В таблице ниже приведены примеры наследования класса и реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cd308-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="cd308-109">Наследование</span><span class="sxs-lookup"><span data-stu-id="cd308-109">Inheritance</span></span>|<span data-ttu-id="cd308-110">Пример</span><span class="sxs-lookup"><span data-stu-id="cd308-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="cd308-111">Нет</span><span class="sxs-lookup"><span data-stu-id="cd308-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="cd308-112">Single</span><span class="sxs-lookup"><span data-stu-id="cd308-112">Single</span></span>|`class DerivedClass: BaseClass { }`|
|<span data-ttu-id="cd308-113">Отсутствует, реализует два интерфейса</span><span class="sxs-lookup"><span data-stu-id="cd308-113">None, implements two interfaces</span></span>|`class ImplClass: IFace1, IFace2 { }`|
|<span data-ttu-id="cd308-114">Одиночное, реализует один интерфейс</span><span class="sxs-lookup"><span data-stu-id="cd308-114">Single, implements one interface</span></span>|`class ImplDerivedClass: BaseClass, IFace1 { }`|

<span data-ttu-id="cd308-115">Классы, объявленные непосредственно в пространстве имен и не вложенные в другие классы, могут быть [открытыми](../../../csharp/language-reference/keywords/public.md) или [внутренними](../../../csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="cd308-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](../../../csharp/language-reference/keywords/public.md) or [internal](../../../csharp/language-reference/keywords/internal.md).</span></span> <span data-ttu-id="cd308-116">По умолчанию классы являются `internal`.</span><span class="sxs-lookup"><span data-stu-id="cd308-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="cd308-117">Члены класса, включая вложенные классы, могут иметь следующие модификаторы доступа: [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md) или `private protected`.</span><span class="sxs-lookup"><span data-stu-id="cd308-117">Class members, including nested classes, can be [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md), or `private protected`.</span></span> <span data-ttu-id="cd308-118">По умолчанию члены являются [закрытыми](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="cd308-118">Members are [private](../../../csharp/language-reference/keywords/private.md) by default.</span></span>

<span data-ttu-id="cd308-119">Дополнительные сведения см. в статье [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cd308-119">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="cd308-120">Можно объявить универсальные классы, имеющие параметры типа.</span><span class="sxs-lookup"><span data-stu-id="cd308-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="cd308-121">Дополнительные сведения см. в разделе [Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="cd308-121">For more information, see [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="cd308-122">Класс может содержать объявления следующих членов:</span><span class="sxs-lookup"><span data-stu-id="cd308-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="cd308-123">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="cd308-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="cd308-124">Константы</span><span class="sxs-lookup"><span data-stu-id="cd308-124">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="cd308-125">Поля</span><span class="sxs-lookup"><span data-stu-id="cd308-125">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="cd308-126">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="cd308-126">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="cd308-127">Методы</span><span class="sxs-lookup"><span data-stu-id="cd308-127">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="cd308-128">Свойства</span><span class="sxs-lookup"><span data-stu-id="cd308-128">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="cd308-129">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="cd308-129">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)

- [<span data-ttu-id="cd308-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="cd308-130">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [<span data-ttu-id="cd308-131">События</span><span class="sxs-lookup"><span data-stu-id="cd308-131">Events</span></span>](../../../csharp/programming-guide/events/index.md)

- [<span data-ttu-id="cd308-132">Делегаты</span><span class="sxs-lookup"><span data-stu-id="cd308-132">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="cd308-133">Классы</span><span class="sxs-lookup"><span data-stu-id="cd308-133">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="cd308-134">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="cd308-134">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

- [<span data-ttu-id="cd308-135">Структуры</span><span class="sxs-lookup"><span data-stu-id="cd308-135">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

## <a name="example"></a><span data-ttu-id="cd308-136">Пример</span><span class="sxs-lookup"><span data-stu-id="cd308-136">Example</span></span>
<span data-ttu-id="cd308-137">В приведенном ниже примере показано объявление полей, конструкторов и методов класса.</span><span class="sxs-lookup"><span data-stu-id="cd308-137">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="cd308-138">В нем также демонстрируется создание экземпляра объекта и печать данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cd308-138">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="cd308-139">В этом примере объявляются два класса.</span><span class="sxs-lookup"><span data-stu-id="cd308-139">In this example, two classes are declared.</span></span> <span data-ttu-id="cd308-140">Первый класс, `Child`, содержит два частных поля (`name` и `age`), два общих конструктора и один общий метод.</span><span class="sxs-lookup"><span data-stu-id="cd308-140">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="cd308-141">Второй класс, `StringTest`, используется для хранения `Main`.</span><span class="sxs-lookup"><span data-stu-id="cd308-141">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]

## <a name="comments"></a><span data-ttu-id="cd308-142">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cd308-142">Comments</span></span>
<span data-ttu-id="cd308-143">Обратите внимание, что в предыдущем примере доступ к частным полям (`name` и `age`) возможен только с помощью общих методов класса `Child`.</span><span class="sxs-lookup"><span data-stu-id="cd308-143">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="cd308-144">Например, имя ребенка нельзя напечатать из метода `Main` с помощью следующего оператора:</span><span class="sxs-lookup"><span data-stu-id="cd308-144">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="cd308-145">Получить доступ к закрытым членам класса `Child` из метода `Main` можно было бы лишь в том случае, если бы `Main` был членом класса.</span><span class="sxs-lookup"><span data-stu-id="cd308-145">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="cd308-146">Типы, объявленные в классе без модификатора доступа, по умолчанию являются `private`, поэтому члены данных в этом примере останутся `private`, если ключевые слова будут удалены.</span><span class="sxs-lookup"><span data-stu-id="cd308-146">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="cd308-147">Наконец, обратите внимание, что для объекта, созданного с помощью конструктора по умолчанию (`child3`), поле age по умолчанию было инициализировано с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="cd308-147">Finally, notice that for the object created using the default constructor (`child3`), the age field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cd308-148">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="cd308-148">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cd308-149">См. также</span><span class="sxs-lookup"><span data-stu-id="cd308-149">See Also</span></span>
 [<span data-ttu-id="cd308-150">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="cd308-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cd308-151">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cd308-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cd308-152">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="cd308-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="cd308-153">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="cd308-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
