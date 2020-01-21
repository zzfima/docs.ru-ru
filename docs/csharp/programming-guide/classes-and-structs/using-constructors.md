---
title: Руководство по программированию на C#. Использование конструкторов
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: faab6ac57629db11c60ee5b563ea95ebb90016dd
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964362"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="a47c1-102">Использование конструкторов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a47c1-102">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="a47c1-103">Каждый раз, когда создается [класс](../../language-reference/keywords/class.md) или [структура](../../language-reference/keywords/struct.md), вызывается конструктор.</span><span class="sxs-lookup"><span data-stu-id="a47c1-103">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="a47c1-104">Конструкторы имеют имя, совпадающее с именем класса или структуры, и обычно инициализируют члены данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="a47c1-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="a47c1-105">В следующем примере класс с именем `Taxi` определяется с помощью простого конструктора.</span><span class="sxs-lookup"><span data-stu-id="a47c1-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="a47c1-106">Затем оператор [new](../../language-reference/operators/new-operator.md) создает экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="a47c1-106">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="a47c1-107">Конструктор `Taxi` вызывается оператором `new` сразу после того, как новому объекту будет выделена память.</span><span class="sxs-lookup"><span data-stu-id="a47c1-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="a47c1-108">Конструктор, который не принимает никаких параметров, называется *конструктором без параметров*.</span><span class="sxs-lookup"><span data-stu-id="a47c1-108">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="a47c1-109">Конструкторы без параметров вызываются всякий раз, когда создается экземпляр объекта с помощью оператора `new`, а аргументы в `new` не передаются.</span><span class="sxs-lookup"><span data-stu-id="a47c1-109">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="a47c1-110">Дополнительные сведения см. в разделе [Конструкторы экземпляров](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-110">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="a47c1-111">Если класс не является [статическим](../../language-reference/keywords/static.md), компилятор C# выделяет классам без конструкторов открытый конструктор без параметров, позволяющий создавать экземпляры классов.</span><span class="sxs-lookup"><span data-stu-id="a47c1-111">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="a47c1-112">Дополнительные сведения см. в статье [Статические классы и члены статических классов](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-112">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="a47c1-113">Создание экземпляров класса можно запретить, сделав конструктор закрытым, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a47c1-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="a47c1-114">Дополнительные сведения см. в разделе [Закрытые конструкторы](./private-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-114">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="a47c1-115">Конструкторы для типов [struct](../../language-reference/keywords/struct.md) похожи на конструкторы классов, однако `structs` не может содержать явный конструктор без параметров, так как он предоставляется компилятором автоматически.</span><span class="sxs-lookup"><span data-stu-id="a47c1-115">Constructors for [struct](../../language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="a47c1-116">Этот конструктор инициализирует каждое поле в `struct` со [значением по умолчанию](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-116">This constructor initializes each field in the `struct` to the [default value](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="a47c1-117">При этом конструктор без параметров вызывается только в том случае, если экземпляр `struct` создается с помощью переменной `new`.</span><span class="sxs-lookup"><span data-stu-id="a47c1-117">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="a47c1-118">Например, в этом коде конструктор без параметров используется для <xref:System.Int32> — это обеспечивает инициализацию целого числа:</span><span class="sxs-lookup"><span data-stu-id="a47c1-118">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="a47c1-119">В то же время следующий код вызывает ошибку компилятора, поскольку не использует `new`, и потому, что использует не инициализированный объект:</span><span class="sxs-lookup"><span data-stu-id="a47c1-119">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="a47c1-120">Кроме того, объекты на основе `structs` (включая все встроенные числовые типы) можно инициализировать или назначить, а затем использовать, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a47c1-120">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="a47c1-121">В связи с этим вызывать конструктор без параметров для типа значения необязательно.</span><span class="sxs-lookup"><span data-stu-id="a47c1-121">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="a47c1-122">Оба класса и `structs` могут определять конструкторы, принимающие параметры.</span><span class="sxs-lookup"><span data-stu-id="a47c1-122">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="a47c1-123">Конструкторы, принимающие параметры, необходимо вызывать с помощью оператора `new` или [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-123">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="a47c1-124">Классы и `structs` могут определять также несколько конструкторов; для определения конструктора без параметров ни один их них не требуется.</span><span class="sxs-lookup"><span data-stu-id="a47c1-124">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="a47c1-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="a47c1-125">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="a47c1-126">Этот класс можно создать, воспользовавшись одним из следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="a47c1-126">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="a47c1-127">Конструктор может использовать ключевое слово `base` для вызова конструктора базового класса.</span><span class="sxs-lookup"><span data-stu-id="a47c1-127">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="a47c1-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="a47c1-128">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="a47c1-129">В этом примере конструктор базового класса вызывается перед выполнением соответствующего ему блока.</span><span class="sxs-lookup"><span data-stu-id="a47c1-129">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="a47c1-130">Ключевое слово `base` можно использовать как с параметрами, так и без них.</span><span class="sxs-lookup"><span data-stu-id="a47c1-130">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="a47c1-131">Любые параметры для конструктора можно использовать как параметры для `base` или как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="a47c1-131">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="a47c1-132">Дополнительные сведения см. в разделе [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-132">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="a47c1-133">В производном классе, если конструктор базового класса не вызывается явным образом с помощью ключевого слова `base`, конструктор без параметров, если он существует, вызывается неявно.</span><span class="sxs-lookup"><span data-stu-id="a47c1-133">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="a47c1-134">Это означает, что следующие объявления конструкторов действуют одинаково:</span><span class="sxs-lookup"><span data-stu-id="a47c1-134">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="a47c1-135">Если базовый класс не предлагает конструктор без параметров, производный класс должен явно вызвать конструктор базового класса с помощью `base`.</span><span class="sxs-lookup"><span data-stu-id="a47c1-135">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="a47c1-136">Конструктор может вызывать другой конструктор в том же объекте с помощью ключевого слова [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-136">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="a47c1-137">Как и `base`, `this` можно использовать с параметрами или без, а все параметры в конструкторе доступны как параметры `this` или как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="a47c1-137">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="a47c1-138">Например, второй конструктор в предыдущем примере можно переписать, используя `this`: </span><span class="sxs-lookup"><span data-stu-id="a47c1-138">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="a47c1-139">Применение ключевого слова `this` в приведенном выше примере привело к вызову конструктора:</span><span class="sxs-lookup"><span data-stu-id="a47c1-139">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="a47c1-140">Конструкторы могут иметь пометку [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) или [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-140">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="a47c1-141">Эти модификаторы доступа определяют, каким образом пользователи класса смогут создавать класс.</span><span class="sxs-lookup"><span data-stu-id="a47c1-141">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="a47c1-142">Дополнительные сведения см. в статье [Модификаторы доступа](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-142">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="a47c1-143">Конструктор можно объявить статическим, используя ключевое слово [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-143">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="a47c1-144">Статические конструкторы вызываются автоматически непосредственно перед доступом к статическим полям и обычно используются для инициализации членов статического класса.</span><span class="sxs-lookup"><span data-stu-id="a47c1-144">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="a47c1-145">Дополнительные сведения см. в разделе [Статические конструкторы](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-145">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a47c1-146">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a47c1-146">C# Language Specification</span></span>  

<span data-ttu-id="a47c1-147">Дополнительные сведения см. в разделах [Конструкторы экземпляров](~/_csharplang/spec/classes.md#instance-constructors) и [Статические конструкторы](~/_csharplang/spec/classes.md#static-constructors) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="a47c1-147">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a47c1-148">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="a47c1-148">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a47c1-149">См. также</span><span class="sxs-lookup"><span data-stu-id="a47c1-149">See also</span></span>

- [<span data-ttu-id="a47c1-150">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a47c1-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a47c1-151">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="a47c1-151">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="a47c1-152">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="a47c1-152">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="a47c1-153">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="a47c1-153">Finalizers</span></span>](./destructors.md)
