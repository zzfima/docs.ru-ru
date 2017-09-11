---
title: "Универсальные классы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
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
ms.openlocfilehash: 17ec9f5d26c01b7f7f7f95026bfdfaa88d709b60
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generic-classes-c-programming-guide"></a><span data-ttu-id="c0beb-102">Универсальные классы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c0beb-102">Generic Classes (C# Programming Guide)</span></span>
<span data-ttu-id="c0beb-103">Универсальные классы инкапсулируют операции, которые не относятся к конкретному типу данных.</span><span class="sxs-lookup"><span data-stu-id="c0beb-103">Generic classes encapsulate operations that are not specific to a particular data type.</span></span> <span data-ttu-id="c0beb-104">Универсальные классы чаще всего используются для работы с коллекциями, такими как связанные списки, хэш-таблицы, стеки, очереди, деревья и т. д.</span><span class="sxs-lookup"><span data-stu-id="c0beb-104">The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on.</span></span> <span data-ttu-id="c0beb-105">Такие операции, как добавление и удаление элементов коллекции, по существу выполняются одинаково, независимо от типа хранимых данных.</span><span class="sxs-lookup"><span data-stu-id="c0beb-105">Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.</span></span>  
  
 <span data-ttu-id="c0beb-106">В большинстве случаев для этого используются классы коллекций. Рекомендуется выбирать те из них, которые представлены в библиотеке классов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0beb-106">For most scenarios that require collection classes, the recommended approach is to use the ones provided in the .NET Framework class library.</span></span> <span data-ttu-id="c0beb-107">Дополнительные сведения об использовании этих классов см. в разделе [Универсальные шаблоны в библиотеке классов платформы .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="c0beb-107">For more information about using these classes, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="c0beb-108">Как правило, при создании универсального класса сначала определяется конкретный класс, после чего его типы поочередно заменяются параметрами типов до тех пор, пока не будет достигнут необходимый баланс между степенью обобщения и удобством работы.</span><span class="sxs-lookup"><span data-stu-id="c0beb-108">Typically, you create generic classes by starting with an existing concrete class, and changing types into type parameters one at a time until you reach the optimal balance of generalization and usability.</span></span> <span data-ttu-id="c0beb-109">При создании собственных универсальных классов необходимо учитывать следующие важные моменты:</span><span class="sxs-lookup"><span data-stu-id="c0beb-109">When creating your own generic classes, important considerations include the following:</span></span>  
  
-   <span data-ttu-id="c0beb-110">Типы, которые требуется обобщить с использованием параметров типа.</span><span class="sxs-lookup"><span data-stu-id="c0beb-110">Which types to generalize into type parameters.</span></span>  
  
     <span data-ttu-id="c0beb-111">Как правило, чем больше типов параметризовано, тем более гибким и универсальным становится ваш код.</span><span class="sxs-lookup"><span data-stu-id="c0beb-111">As a rule, the more types you can parameterize, the more flexible and reusable your code becomes.</span></span> <span data-ttu-id="c0beb-112">Тем не менее слишком высокая степень обобщения может отрицательно сказаться на понятности создаваемого вами кода для других разработчиков.</span><span class="sxs-lookup"><span data-stu-id="c0beb-112">However, too much generalization can create code that is difficult for other developers to read or understand.</span></span>  
  
-   <span data-ttu-id="c0beb-113">Ограничения (если требуются), которые будут применяться к параметрам типа (см. раздел [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="c0beb-113">What constraints, if any, to apply to the type parameters (See [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span></span>  
  
     <span data-ttu-id="c0beb-114">Рекомендуется применять максимально возможный объем ограничений, при котором вы по-прежнему сможете работать с необходимыми типами.</span><span class="sxs-lookup"><span data-stu-id="c0beb-114">A good rule is to apply the maximum constraints possible that will still let you handle the types you must handle.</span></span> <span data-ttu-id="c0beb-115">Например, если универсальный класс будет использоваться только для работы со ссылочными типами, примените ограничение класса.</span><span class="sxs-lookup"><span data-stu-id="c0beb-115">For example, if you know that your generic class is intended for use only with reference types, apply the class constraint.</span></span> <span data-ttu-id="c0beb-116">Это позволит исключить случайное использование класса с типами значений и позволит использовать оператор `as` в отношении `T`, а также проверять наличие значений null.</span><span class="sxs-lookup"><span data-stu-id="c0beb-116">That will prevent unintended use of your class with value types, and will enable you to use the `as` operator on `T`, and check for null values.</span></span>  
  
-   <span data-ttu-id="c0beb-117">Требуется ли разбивать универсальные функции между базовыми классами и подклассами.</span><span class="sxs-lookup"><span data-stu-id="c0beb-117">Whether to factor generic behavior into base classes and subclasses.</span></span>  
  
     <span data-ttu-id="c0beb-118">Поскольку универсальные классы могут выступать в качестве базовых классов, здесь необходимо учитывать те же принципы разработки, что и для классов, не являющихся универсальными.</span><span class="sxs-lookup"><span data-stu-id="c0beb-118">Because generic classes can serve as base classes, the same design considerations apply here as with non-generic classes.</span></span> <span data-ttu-id="c0beb-119">См. описание правил наследования от универсальных базовых классов далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c0beb-119">See the rules about inheriting from generic base classes later in this topic.</span></span>  
  
-   <span data-ttu-id="c0beb-120">Требуется ли реализовывать один или несколько универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="c0beb-120">Whether to implement one or more generic interfaces.</span></span>  
  
     <span data-ttu-id="c0beb-121">Например, при разработке класса, который будет использоваться для создания элементов коллекции на основе универсальных шаблонов, может потребоваться реализовать интерфейс <xref:System.IComparable%601>, где `T` — это тип вашего класса.</span><span class="sxs-lookup"><span data-stu-id="c0beb-121">For example, if you are designing a class that will be used to create items in a generics-based collection, you may have to implement an interface such as <xref:System.IComparable%601> where `T` is the type of your class.</span></span>  
  
 <span data-ttu-id="c0beb-122">Пример простого универсального класса можно найти в разделе [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="c0beb-122">For an example of a simple generic class, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span>  
  
 <span data-ttu-id="c0beb-123">Правила в отношении параметров типа и ограничений влияют на поведение универсального класса, особенно в контексте наследования и доступа к элементам.</span><span class="sxs-lookup"><span data-stu-id="c0beb-123">The rules for type parameters and constraints have several implications for generic class behavior, especially regarding inheritance and member accessibility.</span></span> <span data-ttu-id="c0beb-124">Прежде чем продолжить, необходимо ознакомиться с некоторыми терминами и понятиями.</span><span class="sxs-lookup"><span data-stu-id="c0beb-124">Before proceeding, you should understand some terms.</span></span> <span data-ttu-id="c0beb-125">Ссылка на универсальный класс `Node<T>,` в клиентском коде может задаваться с использованием аргумента типа или путем создания закрытого сконструированного типа (`Node<int>`).</span><span class="sxs-lookup"><span data-stu-id="c0beb-125">For a generic class `Node<T>,` client code can reference the class either by specifying a type argument, to create a closed constructed type (`Node<int>`).</span></span> <span data-ttu-id="c0beb-126">Кроме того, можно не задавать параметр типа (например, при указании универсального базового класса), чтобы определить открытый сконструированный тип (`Node<T>`).</span><span class="sxs-lookup"><span data-stu-id="c0beb-126">Alternatively, it can leave the type parameter unspecified, for example when you specify a generic base class, to create an open constructed type (`Node<T>`).</span></span> <span data-ttu-id="c0beb-127">Универсальные классы могут наследоваться от конкретных, а также закрытых или открытых сконструированных базовых классов:</span><span class="sxs-lookup"><span data-stu-id="c0beb-127">Generic classes can inherit from concrete, closed constructed, or open constructed base classes:</span></span>  
  
 <span data-ttu-id="c0beb-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0beb-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span></span>  
  
 <span data-ttu-id="c0beb-129">Классы, не являющиеся универсальными, то есть конкретные классы, могут наследоваться от закрытых сконструированных базовых классов. Наследование от аналогичных открытых классов или от параметров типа невозможно, поскольку во время выполнения клиентский код не может предоставить аргумент типа, необходимый для создания экземпляра базового класса.</span><span class="sxs-lookup"><span data-stu-id="c0beb-129">Non-generic, in other words, concrete, classes can inherit from closed constructed base classes, but not from open constructed classes or from type parameters because there is no way at run time for client code to supply the type argument required to instantiate the base class.</span></span>  
  
 <span data-ttu-id="c0beb-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0beb-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span></span>  
  
 <span data-ttu-id="c0beb-131">Универсальные классы, наследуемые от открытых сконструированных типов, должны предоставлять аргументы типа для любых параметров типа базового класса, которые не используются совместно с наследующим классом. Это продемонстрировано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c0beb-131">Generic classes that inherit from open constructed types must supply type arguments for any base class type parameters that are not shared by the inheriting class, as demonstrated in the following code:</span></span>  
  
 <span data-ttu-id="c0beb-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0beb-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span></span>  
  
 <span data-ttu-id="c0beb-133">Универсальные классы, наследуемые от открытых сконструированных типов, должны задавать множество ограничений, которые явно или косвенно включают в себя все ограничения базового типа:</span><span class="sxs-lookup"><span data-stu-id="c0beb-133">Generic classes that inherit from open constructed types must specify constraints that are a superset of, or imply, the constraints on the base type:</span></span>  
  
 <span data-ttu-id="c0beb-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0beb-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span></span>  
  
 <span data-ttu-id="c0beb-135">Универсальные типы могут использовать несколько параметров типа и ограничений, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="c0beb-135">Generic types can use multiple type parameters and constraints, as follows:</span></span>  
  
 <span data-ttu-id="c0beb-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0beb-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span></span>  
  
 <span data-ttu-id="c0beb-137">Открытые и закрытые сконструированные типы можно использовать в качестве параметров метода:</span><span class="sxs-lookup"><span data-stu-id="c0beb-137">Open constructed and closed constructed types can be used as method parameters:</span></span>  
  
 <span data-ttu-id="c0beb-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0beb-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span></span>  
  
 <span data-ttu-id="c0beb-139">Если универсальный класс реализует интерфейс, все экземпляры такого класса можно привести к этому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="c0beb-139">If a generic class implements an interface, all instances of that class can be cast to that interface.</span></span>  
  
 <span data-ttu-id="c0beb-140">Универсальные классы инвариантны.</span><span class="sxs-lookup"><span data-stu-id="c0beb-140">Generic classes are invariant.</span></span> <span data-ttu-id="c0beb-141">Другими словами, если входной параметр задает `List<BaseClass>`, при попытке предоставить `List<DerivedClass>` возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="c0beb-141">In other words, if an input parameter specifies a `List<BaseClass>`, you will get a compile-time error if you try to provide a `List<DerivedClass>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0beb-142">См. также</span><span class="sxs-lookup"><span data-stu-id="c0beb-142">See Also</span></span>  
 <span data-ttu-id="c0beb-143"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="c0beb-143"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="c0beb-144">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0beb-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c0beb-145">[Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0beb-145">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="c0beb-146">[Сохранение состояния перечислителей](http://go.microsoft.com/fwlink/?LinkId=112390) </span><span class="sxs-lookup"><span data-stu-id="c0beb-146">[Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390) </span></span>  
 [<span data-ttu-id="c0beb-147">Загадка по наследованию, часть 1</span><span class="sxs-lookup"><span data-stu-id="c0beb-147">An Inheritance Puzzle, Part One</span></span>](http://go.microsoft.com/fwlink/?LinkId=112380)

