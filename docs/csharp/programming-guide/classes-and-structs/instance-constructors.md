---
title: Руководство по программированию на C#. Конструкторы экземпляров
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 621b8ca7510b0b9916c9c46f201ff77402c3c655
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964735"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="bbc31-102">Конструкторы экземпляров (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="bbc31-102">Instance Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="bbc31-103">Конструкторы экземпляров используются для создания и инициализации переменных члена экземпляра, если создание объекта [class](../../language-reference/keywords/class.md) осуществляется с помощью выражения [new](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="bbc31-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../language-reference/operators/new-operator.md) expression to create an object of a [class](../../language-reference/keywords/class.md).</span></span> <span data-ttu-id="bbc31-104">Для инициализации класса [static](../../language-reference/keywords/static.md) или статических переменных в нестатическом классе определяется статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="bbc31-104">To initialize a [static](../../language-reference/keywords/static.md) class, or static variables in a non-static class, you define a static constructor.</span></span> <span data-ttu-id="bbc31-105">Дополнительные сведения см. в разделе [Статические конструкторы](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="bbc31-105">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
 <span data-ttu-id="bbc31-106">В следующем примере показан конструктор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bbc31-106">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> <span data-ttu-id="bbc31-107">Для ясности этот класс содержит открытые поля.</span><span class="sxs-lookup"><span data-stu-id="bbc31-107">For clarity, this class contains public fields.</span></span> <span data-ttu-id="bbc31-108">Открытые поля не рекомендуется использовать на практике, поскольку в этом случае любой метод в любом месте программы получает неограниченный и неконтролируемый доступ к внутренней работе объекта.</span><span class="sxs-lookup"><span data-stu-id="bbc31-108">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="bbc31-109">Члены данных обычно должны быть закрытыми, а доступ к ним должен осуществляться только посредством методов и свойства класса.</span><span class="sxs-lookup"><span data-stu-id="bbc31-109">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="bbc31-110">Этот конструктор экземпляра вызывается каждый раз при создании объекта на базе класса `Coords`.</span><span class="sxs-lookup"><span data-stu-id="bbc31-110">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="bbc31-111">Такой конструктор без аргументов называется *конструктором без параметров*.</span><span class="sxs-lookup"><span data-stu-id="bbc31-111">A constructor like this one, which takes no arguments, is called a *parameterless constructor*.</span></span> <span data-ttu-id="bbc31-112">Зачастую такие конструкторы используются для предоставления дополнительных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="bbc31-112">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="bbc31-113">Например, можно добавить конструктор в класс `Coords`, позволяющий указывать начальные значения для членов данных:</span><span class="sxs-lookup"><span data-stu-id="bbc31-113">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 <span data-ttu-id="bbc31-114">Это позволяет создавать объекты `Coords` с начальными значениями по умолчанию или с другими начальными значениями:</span><span class="sxs-lookup"><span data-stu-id="bbc31-114">This allows `Coords` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 <span data-ttu-id="bbc31-115">Если класс не имеет конструктора, автоматически создается конструктор без параметров и для инициализации полей объекта используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbc31-115">If a class does not have a constructor, a parameterless constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="bbc31-116">Например, [int](../../language-reference/builtin-types/integral-numeric-types.md) инициализируется значением 0.</span><span class="sxs-lookup"><span data-stu-id="bbc31-116">For example, an [int](../../language-reference/builtin-types/integral-numeric-types.md) is initialized to 0.</span></span> <span data-ttu-id="bbc31-117">Дополнительные сведения о значениях по умолчанию типов см. в разделе [Значения по умолчанию типов C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="bbc31-117">For information about the type default values, see [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="bbc31-118">Следовательно, поскольку конструктор без параметров класса `Coords` инициализирует все члены данных с нулевыми значениями, его можно удалить. При этом работа класса не изменится.</span><span class="sxs-lookup"><span data-stu-id="bbc31-118">Therefore, because the `Coords` class parameterless constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="bbc31-119">Полный пример использования нескольких конструкторов см. в данном разделе в примере 1; пример автоматически созданного конструктора см. в примере 2.</span><span class="sxs-lookup"><span data-stu-id="bbc31-119">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="bbc31-120">Конструкторы экземпляров также можно использовать для вызова конструкторов экземпляров базового класса.</span><span class="sxs-lookup"><span data-stu-id="bbc31-120">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="bbc31-121">Конструктор класса может вызвать конструктор базового класса с помощью инициализатора:</span><span class="sxs-lookup"><span data-stu-id="bbc31-121">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 <span data-ttu-id="bbc31-122">В этом примере класс `Circle` передает значения радиуса и высоты конструктору, предоставленному классом `Shape`, для которого класс `Circle` является производным.</span><span class="sxs-lookup"><span data-stu-id="bbc31-122">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="bbc31-123">Полный текст кода с использованием классов `Shape` и `Circle` см. в данном разделе в примере 3.</span><span class="sxs-lookup"><span data-stu-id="bbc31-123">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="bbc31-124">Пример 1</span><span class="sxs-lookup"><span data-stu-id="bbc31-124">Example 1</span></span>  
 <span data-ttu-id="bbc31-125">В следующем примере демонстрируется класс с двумя конструкторами, один из которых не имеет аргументов, а второй имеет два аргумента.</span><span class="sxs-lookup"><span data-stu-id="bbc31-125">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a><span data-ttu-id="bbc31-126">Пример 2</span><span class="sxs-lookup"><span data-stu-id="bbc31-126">Example 2</span></span>  
 <span data-ttu-id="bbc31-127">В этом примере класс `Person` не имеет конструкторов, поэтому автоматически предоставляется конструктор без параметров, а все поля инициализируются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbc31-127">In this example, the class `Person` does not have any constructors, in which case, a parameterless constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 <span data-ttu-id="bbc31-128">Обратите внимание, что значение по умолчанию `age` равно `0`, а значение по умолчанию `name` равно `null`.</span><span class="sxs-lookup"><span data-stu-id="bbc31-128">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="bbc31-129">Пример 3</span><span class="sxs-lookup"><span data-stu-id="bbc31-129">Example 3</span></span>  
 <span data-ttu-id="bbc31-130">В следующем примере демонстрируется использование инициализатора базового класса.</span><span class="sxs-lookup"><span data-stu-id="bbc31-130">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="bbc31-131">Класс `Circle` является производным от основного класса `Shape`, а класс `Cylinder` является производным от класса `Circle`.</span><span class="sxs-lookup"><span data-stu-id="bbc31-131">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="bbc31-132">Конструктор каждого производного класса использует инициализатор своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="bbc31-132">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 <span data-ttu-id="bbc31-133">Дополнительные примеры вызова конструкторов базовых классов см. в разделах [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) и [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="bbc31-133">For more examples on invoking the base class constructors, see [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), and [base](../../language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc31-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bbc31-134">See also</span></span>

- [<span data-ttu-id="bbc31-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bbc31-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bbc31-136">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="bbc31-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="bbc31-137">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="bbc31-137">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="bbc31-138">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="bbc31-138">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="bbc31-139">static</span><span class="sxs-lookup"><span data-stu-id="bbc31-139">static</span></span>](../../language-reference/keywords/static.md)
