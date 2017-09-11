---
title: "Конструкторы экземпляров (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f93f622d5bf99ab7e8b1d8338192ff58472813dd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="b8fe9-102">Конструкторы экземпляров (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="b8fe9-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="b8fe9-103">Конструкторы экземпляров используются для создания и инициализации переменных члена экземпляра, если создание объекта [class](../../../csharp/language-reference/keywords/class.md) осуществляется с помощью выражения [new](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe9-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="b8fe9-104">Для инициализации класса [static](../../../csharp/language-reference/keywords/static.md) или статических переменных в нестатическом классе необходимо определить статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="b8fe9-105">Дополнительные сведения см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe9-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="b8fe9-106">В следующем примере показан конструктор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-106">The following example shows an instance constructor:</span></span>  
  
 <span data-ttu-id="b8fe9-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8fe9-108">Для ясности этот класс содержит открытые поля.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="b8fe9-109">Открытые поля не рекомендуется использовать на практике, поскольку в этом случае любой метод в любом месте программы получает неограниченный и неконтролируемый доступ к внутренней работе объекта.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="b8fe9-110">Члены данных обычно должны быть закрытыми, а доступ к ним должен осуществляться только посредством методов и свойства класса.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="b8fe9-111">Этот конструктор экземпляра вызывается каждый раз при создании объекта на базе класса `CoOrds`.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-111">This instance constructor is called whenever an object based on the `CoOrds` class is created.</span></span> <span data-ttu-id="b8fe9-112">Такой конструктор без аргументов называется *конструктором по умолчанию*.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-112">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="b8fe9-113">Зачастую такие конструкторы используются для предоставления дополнительных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="b8fe9-114">Например, можно добавить конструктор в класс `CoOrds`, позволяющий указывать начальные значения для членов данных:</span><span class="sxs-lookup"><span data-stu-id="b8fe9-114">For example, we can add a constructor to the `CoOrds` class that allows us to specify the initial values for the data members:</span></span>  
  
 <span data-ttu-id="b8fe9-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="b8fe9-116">Это позволяет создавать объекты `CoOrd` с начальными значениями по умолчанию или с другими начальными значениями:</span><span class="sxs-lookup"><span data-stu-id="b8fe9-116">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 <span data-ttu-id="b8fe9-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="b8fe9-118">Если класс не содержит конструктор, автоматически создается конструктор по умолчанию, и для инициализации полей объекта используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-118">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="b8fe9-119">Например, [int](../../../csharp/language-reference/keywords/int.md) инициализируется значением 0.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-119">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="b8fe9-120">Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe9-120">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="b8fe9-121">Следовательно, поскольку конструктор по умолчанию класса `CoOrds` инициализирует все члены данных с нулевыми значениями, его можно удалить, при этом порядок работы класса не изменится.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-121">Therefore, because the `CoOrds` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="b8fe9-122">Полный пример использования нескольких конструкторов см. в данном разделе в примере 1; пример автоматически созданного конструктора см. в примере 2.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-122">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="b8fe9-123">Конструкторы экземпляров также можно использовать для вызова конструкторов экземпляров базового класса.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-123">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="b8fe9-124">Конструктор класса может вызвать конструктор базового класса с помощью инициализатора:</span><span class="sxs-lookup"><span data-stu-id="b8fe9-124">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 <span data-ttu-id="b8fe9-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="b8fe9-126">В этом примере класс `Circle` передает значения радиуса и высоты конструктору, предоставленному классом `Shape`, для которого класс `Circle` является производным.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-126">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="b8fe9-127">Полный текст кода с использованием классов `Shape` и `Circle` см. в данном разделе в примере 3.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-127">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="b8fe9-128">Пример 1</span><span class="sxs-lookup"><span data-stu-id="b8fe9-128">Example 1</span></span>  
 <span data-ttu-id="b8fe9-129">В следующем примере демонстрируется класс с двумя конструкторами, один из которых не имеет аргументов, а второй имеет два аргумента.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-129">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 <span data-ttu-id="b8fe9-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="b8fe9-131">Пример 2</span><span class="sxs-lookup"><span data-stu-id="b8fe9-131">Example 2</span></span>  
 <span data-ttu-id="b8fe9-132">В этом примере класс `Person` не имеет конструкторов, поэтому автоматически предоставляется конструктор по умолчанию, а все поля инициализируются со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-132">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 <span data-ttu-id="b8fe9-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="b8fe9-134">Обратите внимание, что значение по умолчанию `age` равно `0`, а значение по умолчанию `name` равно `null`.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-134">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="b8fe9-135">Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe9-135">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="b8fe9-136">Пример 3</span><span class="sxs-lookup"><span data-stu-id="b8fe9-136">Example 3</span></span>  
 <span data-ttu-id="b8fe9-137">В следующем примере демонстрируется использование инициализатора базового класса.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-137">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="b8fe9-138">Класс `Circle` является производным от основного класса `Shape`, а класс `Cylinder` является производным от класса `Circle`.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-138">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="b8fe9-139">Конструктор каждого производного класса использует инициализатор своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="b8fe9-139">The constructor on each derived class is using its base class initializer.</span></span>  
  
 <span data-ttu-id="b8fe9-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="b8fe9-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="b8fe9-141">Дополнительные примеры вызова конструкторов базовых классов см. в разделах [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) и [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe9-141">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fe9-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b8fe9-142">See Also</span></span>  
 <span data-ttu-id="b8fe9-143">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8fe9-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b8fe9-144">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8fe9-144">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="b8fe9-145">[Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="b8fe9-145">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="b8fe9-146">[Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="b8fe9-146">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 [<span data-ttu-id="b8fe9-147">static</span><span class="sxs-lookup"><span data-stu-id="b8fe9-147">static</span></span>](../../../csharp/language-reference/keywords/static.md)

