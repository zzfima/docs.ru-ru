---
title: "Использование конструкторов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
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
ms.openlocfilehash: 75b55fde2fbd1697aed7eb0665a571c63b9b0b42
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="d25b6-102">Использование конструкторов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d25b6-102">Using Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="d25b6-103">Каждый раз, когда создается [класс](../../../csharp/language-reference/keywords/class.md) или [структура](../../../csharp/language-reference/keywords/struct.md), вызывается конструктор.</span><span class="sxs-lookup"><span data-stu-id="d25b6-103">When a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="d25b6-104">Конструкторы имеют имя, совпадающее с именем класса или структуры, и обычно инициализируют члены данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="d25b6-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="d25b6-105">В следующем примере класс с именем `Taxi` определяется с помощью простого конструктора.</span><span class="sxs-lookup"><span data-stu-id="d25b6-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="d25b6-106">Затем оператор [new](../../../csharp/language-reference/keywords/new.md) создает экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="d25b6-106">This class is then instantiated with the [new](../../../csharp/language-reference/keywords/new.md) operator.</span></span> <span data-ttu-id="d25b6-107">Конструктор `Taxi` вызывается оператором `new` сразу после того, как новому объекту будет выделена память.</span><span class="sxs-lookup"><span data-stu-id="d25b6-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 <span data-ttu-id="d25b6-108">[!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-108">[!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-109">Конструктор, который не принимает никаких параметров, называется *конструктором по умолчанию*.</span><span class="sxs-lookup"><span data-stu-id="d25b6-109">A constructor that takes no parameters is called a *default constructor*.</span></span> <span data-ttu-id="d25b6-110">Конструкторы по умолчанию вызываются всякий раз, когда создается экземпляр объекта с помощью оператора `new`, а аргументы в `new` не передаются.</span><span class="sxs-lookup"><span data-stu-id="d25b6-110">Default constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="d25b6-111">Дополнительные сведения см. в разделе [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-111">For more information, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="d25b6-112">Если класс является [статическим](../../../csharp/language-reference/keywords/static.md), компилятор C# выделяет классам без конструкторов открытый конструктор по умолчанию, позволяющий создавать экземпляры классов.</span><span class="sxs-lookup"><span data-stu-id="d25b6-112">Unless the class is [static](../../../csharp/language-reference/keywords/static.md), classes without constructors are given a public default constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="d25b6-113">Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-113">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="d25b6-114">Создание экземпляров класса можно запретить, сделав конструктор закрытым, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d25b6-114">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 <span data-ttu-id="d25b6-115">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-115">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-116">Дополнительные сведения см. в разделе [Закрытые конструкторы](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-116">For more information, see [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).</span></span>  
  
 <span data-ttu-id="d25b6-117">Конструкторы для типов [struct](../../../csharp/language-reference/keywords/struct.md) похожи на конструкторы классов, однако `structs` не может содержать явный конструктор по умолчанию, поскольку предоставляется компилятором автоматически.</span><span class="sxs-lookup"><span data-stu-id="d25b6-117">Constructors for [struct](../../../csharp/language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit default constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="d25b6-118">Этот конструктор инициализирует каждое поле в `struct` со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d25b6-118">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="d25b6-119">Дополнительные сведения см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-119">For more information, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="d25b6-120">При этом конструктор по умолчанию вызывается только в том случае, если `struct` создается с помощью переменной `new`.</span><span class="sxs-lookup"><span data-stu-id="d25b6-120">However, this default constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="d25b6-121">Например, в этом коде конструктор по умолчанию используется для <xref:System.Int32> — это обеспечивает инициализацию целого числа:</span><span class="sxs-lookup"><span data-stu-id="d25b6-121">For example, this code uses the default constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="d25b6-122">В то же время следующий код вызывает ошибку компилятора, поскольку не использует `new`, и потому, что использует не инициализированный объект:</span><span class="sxs-lookup"><span data-stu-id="d25b6-122">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="d25b6-123">Кроме того, объекты на основе `structs` (включая все встроенные числовые типы) можно инициализировать или назначить, а затем использовать, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d25b6-123">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="d25b6-124">В связи с этим вызывать конструктор по умолчанию для типа значения необязательно.</span><span class="sxs-lookup"><span data-stu-id="d25b6-124">So calling the default constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="d25b6-125">Оба класса и `structs` могут определять конструкторы, принимающие параметры.</span><span class="sxs-lookup"><span data-stu-id="d25b6-125">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="d25b6-126">Конструкторы, принимающие параметры, необходимо вызывать с помощью оператора `new` или [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-126">Constructors that take parameters must be called through a `new` statement or a [base](../../../csharp/language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="d25b6-127">Классы и `structs` могут определять также несколько конструкторов; для определения конструктора по умолчанию ни один их них не требуется.</span><span class="sxs-lookup"><span data-stu-id="d25b6-127">Classes and `structs` can also define multiple constructors, and neither is required to define a default constructor.</span></span> <span data-ttu-id="d25b6-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="d25b6-128">For example:</span></span>  
  
 <span data-ttu-id="d25b6-129">[!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-129">[!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-130">Этот класс можно создать, воспользовавшись одним из следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="d25b6-130">This class can be created by using either of the following statements:</span></span>  
  
 <span data-ttu-id="d25b6-131">[!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-131">[!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-132">Конструктор может использовать ключевое слово `base` для вызова конструктора базового класса.</span><span class="sxs-lookup"><span data-stu-id="d25b6-132">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="d25b6-133">Например:</span><span class="sxs-lookup"><span data-stu-id="d25b6-133">For example:</span></span>  
  
 <span data-ttu-id="d25b6-134">[!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-134">[!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-135">В этом примере конструктор базового класса вызывается перед выполнением соответствующего ему блока.</span><span class="sxs-lookup"><span data-stu-id="d25b6-135">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="d25b6-136">Ключевое слово `base` можно использовать как с параметрами, так и без них.</span><span class="sxs-lookup"><span data-stu-id="d25b6-136">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="d25b6-137">Любые параметры для конструктора можно использовать как параметры для `base` или как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="d25b6-137">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="d25b6-138">Дополнительные сведения см. в разделе [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-138">For more information, see [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="d25b6-139">В производном классе, если конструктор базового класса не вызывается явным образом с помощью ключевого слова `base`, конструктор по умолчанию, если он существует, вызывается неявно.</span><span class="sxs-lookup"><span data-stu-id="d25b6-139">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the default constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="d25b6-140">Это означает, что следующие объявления конструкторов действуют одинаково:</span><span class="sxs-lookup"><span data-stu-id="d25b6-140">This means that the following constructor declarations are effectively the same:</span></span>  
  
 <span data-ttu-id="d25b6-141">[!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-141">[!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-142">[!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-142">[!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-143">Если базовый класс не предлагает конструктор по умолчанию, производный класс должен явно вызвать конструктор базового класса с помощью `base`.</span><span class="sxs-lookup"><span data-stu-id="d25b6-143">If a base class does not offer a default constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="d25b6-144">Конструктор может вызывать другой конструктор в том же объекте с помощью [этого](../../../csharp/language-reference/keywords/this.md) ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="d25b6-144">A constructor can invoke another constructor in the same object by using the [this](../../../csharp/language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="d25b6-145">Как и `base`, `this` можно использовать с параметрами или без, а все параметры в конструкторе доступны как параметры `this` или как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="d25b6-145">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="d25b6-146">Например, второй конструктор в предыдущем примере можно переписать, используя `this`:</span><span class="sxs-lookup"><span data-stu-id="d25b6-146">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 <span data-ttu-id="d25b6-147">[!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-147">[!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-148">Применение ключевого слова `this` в приведенном выше примере привело к вызову конструктора:</span><span class="sxs-lookup"><span data-stu-id="d25b6-148">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 <span data-ttu-id="d25b6-149">[!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="d25b6-149">[!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]</span></span>  
  
 <span data-ttu-id="d25b6-150">Конструкторы могут иметь пометку [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="d25b6-150">Constructors can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="d25b6-151">Эти модификаторы доступа определяют, каким образом пользователи класса смогут создавать класс.</span><span class="sxs-lookup"><span data-stu-id="d25b6-151">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="d25b6-152">Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-152">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="d25b6-153">Конструктор можно объявить статическим, используя ключевое слово [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-153">A constructor can be declared static by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="d25b6-154">Статические конструкторы вызываются автоматически непосредственно перед доступом к статическим полям и обычно используются для инициализации членов статического класса.</span><span class="sxs-lookup"><span data-stu-id="d25b6-154">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="d25b6-155">Дополнительные сведения см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="d25b6-155">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d25b6-156">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d25b6-156">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d25b6-157">См. также</span><span class="sxs-lookup"><span data-stu-id="d25b6-157">See Also</span></span>  
 <span data-ttu-id="d25b6-158">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d25b6-158">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d25b6-159">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="d25b6-159">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="d25b6-160">[Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="d25b6-160">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="d25b6-161">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="d25b6-161">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

