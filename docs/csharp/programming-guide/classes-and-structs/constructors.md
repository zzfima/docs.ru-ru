---
title: Руководство по программированию на C#. Конструкторы
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 465dbb9120e6e81e5ef216c34dc6a92283956033
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964676"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="fbbc1-102">Конструкторы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="fbbc1-102">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="fbbc1-103">Каждый раз, когда создается [класс](../../language-reference/keywords/class.md) или [структура](../../language-reference/keywords/struct.md), вызывается конструктор.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-103">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="fbbc1-104">Класс или структура может иметь несколько конструкторов, принимающих различные аргументы.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="fbbc1-105">Конструкторы позволяют программисту задавать значения по умолчанию, ограничивать число установок и писать код, который является гибким и удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="fbbc1-106">Дополнительные сведения и примеры см. в разделах [Использование конструкторов](./using-constructors.md) и [Конструкторы экземпляров](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc1-106">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="fbbc1-107">Конструкторы без параметров</span><span class="sxs-lookup"><span data-stu-id="fbbc1-107">Parameterless constructors</span></span>
  
<span data-ttu-id="fbbc1-108">Если не предоставить конструктор для класса, C# создаст конструктор по умолчанию, который создает экземпляр объекта и задает переменным-членам значения по умолчанию, как показано в статье [Значения по умолчанию типов C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc1-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="fbbc1-109">Если не предоставить конструктор для структуры, C# будет использовать *неявный конструктор без параметров*, чтобы автоматически инициализировать каждое поле значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-109">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="fbbc1-110">Дополнительные сведения и примеры см. в разделе [Конструкторы экземпляров](instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc1-110">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="fbbc1-111">Синтаксис конструктора</span><span class="sxs-lookup"><span data-stu-id="fbbc1-111">Constructor syntax</span></span>

<span data-ttu-id="fbbc1-112">Конструктор — это метод, имя которого совпадает с именем его типа.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="fbbc1-113">Его сигнатура метода содержит только имя метода и список параметров. Она не содержит возвращаемый тип.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="fbbc1-114">В приведенном ниже примере демонстрируется конструктор для класса с именем `Person`.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="fbbc1-115">Если конструктор поддерживает реализацию в виде оператора, можно использовать [определение тела выражения](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc1-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="fbbc1-116">В следующем примере определяется класс `Location`, конструктор которого имеет один строковый параметр *name*.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="fbbc1-117">Определение тела выражения присваивает аргумент полю `locationName`.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="fbbc1-118">Статические конструкторы</span><span class="sxs-lookup"><span data-stu-id="fbbc1-118">Static constructors</span></span>

<span data-ttu-id="fbbc1-119">В приведенных выше примерах показаны конструкторы экземпляров, которые создают новый объект.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="fbbc1-120">В классе или структуре также может быть статический конструктор, который инициализирует статические члены типа.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="fbbc1-121">Статические конструкторы не имеют параметров.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-121">Static constructors are parameterless.</span></span> <span data-ttu-id="fbbc1-122">Если вы не предоставили статический конструктор для инициализации статических полей, компилятор C# инициализирует статические поля значениями по умолчанию, как показано в статье [Значения по умолчанию типов C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc1-122">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="fbbc1-123">В следующем примере статический конструктор используется для инициализации статического поля.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="fbbc1-124">Можно также определить статический конструктор с помощью определения тела выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fbbc1-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="fbbc1-125">Дополнительные сведения и примеры см. в разделе [Статические конструкторы](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc1-125">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbbc1-126">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fbbc1-126">In This Section</span></span>  
 [<span data-ttu-id="fbbc1-127">Использование конструкторов</span><span class="sxs-lookup"><span data-stu-id="fbbc1-127">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="fbbc1-128">Конструкторы экземпляров</span><span class="sxs-lookup"><span data-stu-id="fbbc1-128">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="fbbc1-129">Закрытые конструкторы</span><span class="sxs-lookup"><span data-stu-id="fbbc1-129">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="fbbc1-130">Статические конструкторы</span><span class="sxs-lookup"><span data-stu-id="fbbc1-130">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="fbbc1-131">Практическое руководство. Создание конструктора копий</span><span class="sxs-lookup"><span data-stu-id="fbbc1-131">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="fbbc1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="fbbc1-132">See also</span></span>

- [<span data-ttu-id="fbbc1-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fbbc1-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fbbc1-134">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="fbbc1-134">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="fbbc1-135">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="fbbc1-135">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="fbbc1-136">static</span><span class="sxs-lookup"><span data-stu-id="fbbc1-136">static</span></span>](../../language-reference/keywords/static.md)
- <span data-ttu-id="fbbc1-137">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one) (Почему инициализаторы выполняются в порядке, обратном действию конструкторов? Часть 1)</span><span class="sxs-lookup"><span data-stu-id="fbbc1-137">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)</span></span>
