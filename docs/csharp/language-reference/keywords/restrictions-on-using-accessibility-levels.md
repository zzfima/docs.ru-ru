---
title: "Ограничения на использование уровней доступности (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44d065429f67d717d7c50e3877294eadd462a99d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="5fbca-102">Ограничения на использование уровней доступности (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5fbca-102">Restrictions on Using Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="5fbca-103">При задании типа в объявлении необходимо проверить, зависит ли уровень доступности типа от уровня доступности члена или другого типа.</span><span class="sxs-lookup"><span data-stu-id="5fbca-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="5fbca-104">Например, прямой базовый класс должен иметь по крайней мере такой же уровень доступности, как и производный класс.</span><span class="sxs-lookup"><span data-stu-id="5fbca-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="5fbca-105">Следующие объявления вызывают ошибку компиляции, так как базовый класс `BaseClass` менее доступен, чем `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="5fbca-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 <span data-ttu-id="5fbca-106">В таблице ниже приведены все ограничения на объявленные уровни доступности.</span><span class="sxs-lookup"><span data-stu-id="5fbca-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>  
  
|<span data-ttu-id="5fbca-107">Контекст</span><span class="sxs-lookup"><span data-stu-id="5fbca-107">Context</span></span>|<span data-ttu-id="5fbca-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5fbca-108">Remarks</span></span>|  
|-------------|-------------|  
|[<span data-ttu-id="5fbca-109">Классы</span><span class="sxs-lookup"><span data-stu-id="5fbca-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="5fbca-110">Прямой базовый класс для типа класса должен иметь по крайней мере такой же уровень доступности, как и сам тип класса.</span><span class="sxs-lookup"><span data-stu-id="5fbca-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|  
|[<span data-ttu-id="5fbca-111">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="5fbca-111">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)|<span data-ttu-id="5fbca-112">Явные базовые интерфейсы для типа интерфейса должны иметь по крайней мере такой же уровень доступности, как и сам тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5fbca-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|  
|[<span data-ttu-id="5fbca-113">Делегаты</span><span class="sxs-lookup"><span data-stu-id="5fbca-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)|<span data-ttu-id="5fbca-114">Тип возвращаемого значения и типы параметров для типа делегата должны иметь по крайней мере такой же уровень доступности, как и сам тип делегата.</span><span class="sxs-lookup"><span data-stu-id="5fbca-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|  
|[<span data-ttu-id="5fbca-115">Константы</span><span class="sxs-lookup"><span data-stu-id="5fbca-115">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="5fbca-116">Тип константы должен иметь по крайней мере такой же уровень доступности, как и сама константа.</span><span class="sxs-lookup"><span data-stu-id="5fbca-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|  
|[<span data-ttu-id="5fbca-117">Поля</span><span class="sxs-lookup"><span data-stu-id="5fbca-117">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="5fbca-118">Тип поля должен иметь по крайней мере такой же уровень доступности, как и само поле.</span><span class="sxs-lookup"><span data-stu-id="5fbca-118">The type of a field must be at least as accessible as the field itself.</span></span>|  
|[<span data-ttu-id="5fbca-119">Методы</span><span class="sxs-lookup"><span data-stu-id="5fbca-119">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="5fbca-120">Тип возвращаемого значения и типы параметров для метода должны иметь по крайней мере такой же уровень доступности, как и сам метод.</span><span class="sxs-lookup"><span data-stu-id="5fbca-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|  
|[<span data-ttu-id="5fbca-121">Свойства</span><span class="sxs-lookup"><span data-stu-id="5fbca-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="5fbca-122">Тип свойства должен иметь по крайней мере такой же уровень доступности, как и само свойство.</span><span class="sxs-lookup"><span data-stu-id="5fbca-122">The type of a property must be at least as accessible as the property itself.</span></span>|  
|[<span data-ttu-id="5fbca-123">События</span><span class="sxs-lookup"><span data-stu-id="5fbca-123">Events</span></span>](../../../csharp/programming-guide/events/index.md)|<span data-ttu-id="5fbca-124">Тип события должен иметь по крайней мере такой же уровень доступности, как и само событие.</span><span class="sxs-lookup"><span data-stu-id="5fbca-124">The type of an event must be at least as accessible as the event itself.</span></span>|  
|[<span data-ttu-id="5fbca-125">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="5fbca-125">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)|<span data-ttu-id="5fbca-126">Тип и типы параметров для индексатора должны иметь по крайней мере такой же уровень доступности, как и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="5fbca-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|  
|[<span data-ttu-id="5fbca-127">Операторы</span><span class="sxs-lookup"><span data-stu-id="5fbca-127">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="5fbca-128">Тип возвращаемого значения и типы параметров для оператора должны иметь по крайней мере такой же уровень доступности, как и сам оператор.</span><span class="sxs-lookup"><span data-stu-id="5fbca-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|  
|[<span data-ttu-id="5fbca-129">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="5fbca-129">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="5fbca-130">Типы параметров для конструктора должны иметь по крайней мере такой же уровень доступности, как и сам конструктор.</span><span class="sxs-lookup"><span data-stu-id="5fbca-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5fbca-131">Пример</span><span class="sxs-lookup"><span data-stu-id="5fbca-131">Example</span></span>  
 <span data-ttu-id="5fbca-132">В приведенном ниже примере содержатся ошибочные объявления различных типов.</span><span class="sxs-lookup"><span data-stu-id="5fbca-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="5fbca-133">В комментарии после каждого объявления указывается предполагаемая ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="5fbca-133">The comment following each declaration indicates the expected compiler error.</span></span>  
  
```  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="5fbca-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5fbca-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5fbca-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5fbca-135">See Also</span></span>  
 [<span data-ttu-id="5fbca-136">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5fbca-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5fbca-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5fbca-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5fbca-138">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="5fbca-138">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5fbca-139">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="5fbca-139">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="5fbca-140">Домен доступности</span><span class="sxs-lookup"><span data-stu-id="5fbca-140">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="5fbca-141">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="5fbca-141">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="5fbca-142">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="5fbca-142">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="5fbca-143">public</span><span class="sxs-lookup"><span data-stu-id="5fbca-143">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="5fbca-144">private</span><span class="sxs-lookup"><span data-stu-id="5fbca-144">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="5fbca-145">protected</span><span class="sxs-lookup"><span data-stu-id="5fbca-145">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="5fbca-146">internal</span><span class="sxs-lookup"><span data-stu-id="5fbca-146">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
