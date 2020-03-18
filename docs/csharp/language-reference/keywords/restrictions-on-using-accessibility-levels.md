---
title: Справочник по C#. Ограничения на использование уровней доступности
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 48ab765db7c839ed0dd14df5e6b30f5bd6c0d29b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173540"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="ca98b-102">Ограничения на использование уровней доступности (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ca98b-102">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="ca98b-103">При задании типа в объявлении необходимо проверить, зависит ли уровень доступности типа от уровня доступности члена или другого типа.</span><span class="sxs-lookup"><span data-stu-id="ca98b-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="ca98b-104">Например, прямой базовый класс должен иметь по крайней мере такой же уровень доступности, как и производный класс.</span><span class="sxs-lookup"><span data-stu-id="ca98b-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="ca98b-105">Следующие объявления вызывают ошибку компиляции, так как базовый класс `BaseClass` менее доступен, чем `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="ca98b-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="ca98b-106">В таблице ниже приведены все ограничения на объявленные уровни доступности.</span><span class="sxs-lookup"><span data-stu-id="ca98b-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="ca98b-107">Контекст</span><span class="sxs-lookup"><span data-stu-id="ca98b-107">Context</span></span>|<span data-ttu-id="ca98b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca98b-108">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="ca98b-109">Классы</span><span class="sxs-lookup"><span data-stu-id="ca98b-109">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="ca98b-110">Прямой базовый класс для типа класса должен иметь по крайней мере такой же уровень доступности, как и сам тип класса.</span><span class="sxs-lookup"><span data-stu-id="ca98b-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="ca98b-111">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ca98b-111">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="ca98b-112">Явные базовые интерфейсы для типа интерфейса должны иметь по крайней мере такой же уровень доступности, как и сам тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ca98b-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="ca98b-113">Делегаты</span><span class="sxs-lookup"><span data-stu-id="ca98b-113">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="ca98b-114">Тип возвращаемого значения и типы параметров для типа делегата должны иметь по крайней мере такой же уровень доступности, как и сам тип делегата.</span><span class="sxs-lookup"><span data-stu-id="ca98b-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="ca98b-115">Константы</span><span class="sxs-lookup"><span data-stu-id="ca98b-115">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="ca98b-116">Тип константы должен иметь по крайней мере такой же уровень доступности, как и сама константа.</span><span class="sxs-lookup"><span data-stu-id="ca98b-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="ca98b-117">Поля</span><span class="sxs-lookup"><span data-stu-id="ca98b-117">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="ca98b-118">Тип поля должен иметь по крайней мере такой же уровень доступности, как и само поле.</span><span class="sxs-lookup"><span data-stu-id="ca98b-118">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="ca98b-119">Методы</span><span class="sxs-lookup"><span data-stu-id="ca98b-119">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="ca98b-120">Тип возвращаемого значения и типы параметров для метода должны иметь по крайней мере такой же уровень доступности, как и сам метод.</span><span class="sxs-lookup"><span data-stu-id="ca98b-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="ca98b-121">Свойства</span><span class="sxs-lookup"><span data-stu-id="ca98b-121">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="ca98b-122">Тип свойства должен иметь по крайней мере такой же уровень доступности, как и само свойство.</span><span class="sxs-lookup"><span data-stu-id="ca98b-122">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="ca98b-123">События</span><span class="sxs-lookup"><span data-stu-id="ca98b-123">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="ca98b-124">Тип события должен иметь по крайней мере такой же уровень доступности, как и само событие.</span><span class="sxs-lookup"><span data-stu-id="ca98b-124">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="ca98b-125">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="ca98b-125">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="ca98b-126">Тип и типы параметров для индексатора должны иметь по крайней мере такой же уровень доступности, как и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="ca98b-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="ca98b-127">Операторы</span><span class="sxs-lookup"><span data-stu-id="ca98b-127">Operators</span></span>](../operators/index.md)|<span data-ttu-id="ca98b-128">Тип возвращаемого значения и типы параметров для оператора должны иметь по крайней мере такой же уровень доступности, как и сам оператор.</span><span class="sxs-lookup"><span data-stu-id="ca98b-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="ca98b-129">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="ca98b-129">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="ca98b-130">Типы параметров для конструктора должны иметь по крайней мере такой же уровень доступности, как и сам конструктор.</span><span class="sxs-lookup"><span data-stu-id="ca98b-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="ca98b-131">Пример</span><span class="sxs-lookup"><span data-stu-id="ca98b-131">Example</span></span>

<span data-ttu-id="ca98b-132">В приведенном ниже примере содержатся ошибочные объявления различных типов.</span><span class="sxs-lookup"><span data-stu-id="ca98b-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="ca98b-133">В комментарии после каждого объявления указывается предполагаемая ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="ca98b-133">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="ca98b-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ca98b-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ca98b-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca98b-135">See also</span></span>

- [<span data-ttu-id="ca98b-136">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ca98b-136">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="ca98b-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ca98b-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ca98b-138">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ca98b-138">C# Keywords</span></span>](../../language-reference/keywords/index.md)
- [<span data-ttu-id="ca98b-139">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="ca98b-139">Access Modifiers</span></span>](../../language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="ca98b-140">Домен доступности</span><span class="sxs-lookup"><span data-stu-id="ca98b-140">Accessibility Domain</span></span>](../../language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="ca98b-141">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="ca98b-141">Accessibility Levels</span></span>](../../language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="ca98b-142">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="ca98b-142">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="ca98b-143">public</span><span class="sxs-lookup"><span data-stu-id="ca98b-143">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="ca98b-144">private</span><span class="sxs-lookup"><span data-stu-id="ca98b-144">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="ca98b-145">protected</span><span class="sxs-lookup"><span data-stu-id="ca98b-145">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="ca98b-146">internal</span><span class="sxs-lookup"><span data-stu-id="ca98b-146">internal</span></span>](../../language-reference/keywords/internal.md)
