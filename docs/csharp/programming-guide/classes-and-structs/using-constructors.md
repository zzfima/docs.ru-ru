---
title: Руководство по программированию на C#. Использование конструкторов
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 7d027a67e533cb1ed7b2cea38112b4f585bf5fbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714644"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="0cfa7-102">Использование конструкторов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0cfa7-102">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="0cfa7-103">Каждый раз, когда создается [класс](../../language-reference/keywords/class.md) или [структура](../../language-reference/keywords/struct.md), вызывается конструктор.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-103">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="0cfa7-104">Конструкторы имеют имя, совпадающее с именем класса или структуры, и обычно инициализируют члены данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="0cfa7-105">В следующем примере класс с именем `Taxi` определяется с помощью простого конструктора.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="0cfa7-106">Затем оператор [new](../../language-reference/operators/new-operator.md) создает экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-106">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="0cfa7-107">Конструктор `Taxi` вызывается оператором `new` сразу после того, как новому объекту будет выделена память.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="0cfa7-108">Конструктор, который не принимает никаких параметров, называется *конструктором без параметров*.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-108">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="0cfa7-109">Конструкторы без параметров вызываются всякий раз, когда создается экземпляр объекта с помощью оператора `new`, а аргументы в `new` не передаются.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-109">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="0cfa7-110">Дополнительные сведения см. в разделе [Конструкторы экземпляров](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-110">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="0cfa7-111">Если класс не является [статическим](../../language-reference/keywords/static.md), компилятор C# выделяет классам без конструкторов открытый конструктор без параметров, позволяющий создавать экземпляры классов.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-111">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="0cfa7-112">Дополнительные сведения см. в статье [Статические классы и члены статических классов](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-112">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="0cfa7-113">Создание экземпляров класса можно запретить, сделав конструктор закрытым, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="0cfa7-114">Дополнительные сведения см. в разделе [Закрытые конструкторы](./private-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-114">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="0cfa7-115">Конструкторы для типов [struct](../../language-reference/keywords/struct.md) похожи на конструкторы классов, однако `structs` не может содержать явный конструктор без параметров, так как он предоставляется компилятором автоматически.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-115">Constructors for [struct](../../language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="0cfa7-116">Этот конструктор инициализирует каждое поле в `struct` со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-116">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="0cfa7-117">Дополнительные сведения см. в разделе [Таблица значений по умолчанию](../../language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-117">For more information, see [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="0cfa7-118">При этом конструктор без параметров вызывается только в том случае, если экземпляр `struct` создается с помощью переменной `new`.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-118">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="0cfa7-119">Например, в этом коде конструктор без параметров используется для <xref:System.Int32> — это обеспечивает инициализацию целого числа:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-119">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="0cfa7-120">В то же время следующий код вызывает ошибку компилятора, поскольку не использует `new`, и потому, что использует не инициализированный объект:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-120">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="0cfa7-121">Кроме того, объекты на основе `structs` (включая все встроенные числовые типы) можно инициализировать или назначить, а затем использовать, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-121">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="0cfa7-122">В связи с этим вызывать конструктор без параметров для типа значения необязательно.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-122">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="0cfa7-123">Оба класса и `structs` могут определять конструкторы, принимающие параметры.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-123">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="0cfa7-124">Конструкторы, принимающие параметры, необходимо вызывать с помощью оператора `new` или [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-124">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="0cfa7-125">Классы и `structs` могут определять также несколько конструкторов; для определения конструктора без параметров ни один их них не требуется.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-125">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="0cfa7-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="0cfa7-127">Этот класс можно создать, воспользовавшись одним из следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-127">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="0cfa7-128">Конструктор может использовать ключевое слово `base` для вызова конструктора базового класса.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-128">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="0cfa7-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="0cfa7-130">В этом примере конструктор базового класса вызывается перед выполнением соответствующего ему блока.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-130">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="0cfa7-131">Ключевое слово `base` можно использовать как с параметрами, так и без них.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-131">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="0cfa7-132">Любые параметры для конструктора можно использовать как параметры для `base` или как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-132">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="0cfa7-133">Дополнительные сведения см. в разделе [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-133">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="0cfa7-134">В производном классе, если конструктор базового класса не вызывается явным образом с помощью ключевого слова `base`, конструктор без параметров, если он существует, вызывается неявно.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-134">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="0cfa7-135">Это означает, что следующие объявления конструкторов действуют одинаково:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-135">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="0cfa7-136">Если базовый класс не предлагает конструктор без параметров, производный класс должен явно вызвать конструктор базового класса с помощью `base`.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-136">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="0cfa7-137">Конструктор может вызывать другой конструктор в том же объекте с помощью ключевого слова [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-137">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="0cfa7-138">Как и `base`, `this` можно использовать с параметрами или без, а все параметры в конструкторе доступны как параметры `this` или как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-138">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="0cfa7-139">Например, второй конструктор в предыдущем примере можно переписать, используя `this`:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-139">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="0cfa7-140">Применение ключевого слова `this` в приведенном выше примере привело к вызову конструктора:</span><span class="sxs-lookup"><span data-stu-id="0cfa7-140">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="0cfa7-141">Конструкторы могут иметь пометку [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) или [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-141">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="0cfa7-142">Эти модификаторы доступа определяют, каким образом пользователи класса смогут создавать класс.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-142">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="0cfa7-143">Дополнительные сведения см. в статье [Модификаторы доступа](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-143">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="0cfa7-144">Конструктор можно объявить статическим, используя ключевое слово [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-144">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="0cfa7-145">Статические конструкторы вызываются автоматически непосредственно перед доступом к статическим полям и обычно используются для инициализации членов статического класса.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-145">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="0cfa7-146">Дополнительные сведения см. в разделе [Статические конструкторы](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-146">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0cfa7-147">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0cfa7-147">C# Language Specification</span></span>  

<span data-ttu-id="0cfa7-148">Дополнительные сведения см. в разделах [Конструкторы экземпляров](~/_csharplang/spec/classes.md#instance-constructors) и [Статические конструкторы](~/_csharplang/spec/classes.md#static-constructors) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="0cfa7-148">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="0cfa7-149">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="0cfa7-149">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0cfa7-150">См. также</span><span class="sxs-lookup"><span data-stu-id="0cfa7-150">See also</span></span>

- [<span data-ttu-id="0cfa7-151">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0cfa7-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0cfa7-152">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="0cfa7-152">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="0cfa7-153">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="0cfa7-153">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="0cfa7-154">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="0cfa7-154">Finalizers</span></span>](./destructors.md)
