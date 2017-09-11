---
title: "Преимущества универсальных шаблонов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
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
ms.openlocfilehash: 8b05a3a695064764618564293e6ccd92e2ce60be
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="9cac5-102">Преимущества универсальных шаблонов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9cac5-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="9cac5-103">Универсальные шаблоны позволяют обойти ограничение, существовавшее в более ранних версиях общеязыковой среды выполнения (CLR) и языка C#, из-за которого обобщение реализовывалось путем приведения типов к универсальному базовому типу <xref:System.Object> или из него.</span><span class="sxs-lookup"><span data-stu-id="9cac5-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="9cac5-104">Создавая универсальный класс, вы можете создать коллекцию, которая будет типобезопасной во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="9cac5-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="9cac5-105">Ограничение на использование классов коллекции, не являющихся универсальными, можно продемонстрировать на примере небольшой программы, в которой используется класс коллекции <xref:System.Collections.ArrayList> из библиотеки платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9cac5-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET Framework class library.</span></span> <span data-ttu-id="9cac5-106"><xref:System.Collections.ArrayList> — это очень удобный класс коллекции, который можно использовать без изменений для хранения любых типов значений и ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="9cac5-106"><xref:System.Collections.ArrayList> is a highly convenient collection class that can be used without modification to store any reference or value type.</span></span>  
  
 <span data-ttu-id="9cac5-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9cac5-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span></span>  
  
 <span data-ttu-id="9cac5-108">Тем не менее его применение имеет свои недостатки.</span><span class="sxs-lookup"><span data-stu-id="9cac5-108">But this convenience comes at a cost.</span></span> <span data-ttu-id="9cac5-109">Любые типы значений или ссылочные типы, которые добавляются в <xref:System.Collections.ArrayList>, неявно приводятся с повышением к типу <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="9cac5-109">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="9cac5-110">Если элементы представляют собой типы значений, их необходимо упаковывать при добавлении в список и распаковывать при извлечении из него.</span><span class="sxs-lookup"><span data-stu-id="9cac5-110">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="9cac5-111">Выполнение операций приведения, упаковки-преобразования и распаковки-преобразования отрицательно сказывается на производительности, причем последние две операции при работе с большими коллекциями могут приводить к ее заметному снижению.</span><span class="sxs-lookup"><span data-stu-id="9cac5-111">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="9cac5-112">Еще одно ограничение связано с отсутствием проверки типов во время компиляции. Поскольку <xref:System.Collections.ArrayList> приводит все элементы к типу <xref:System.Object>, во время компиляции невозможно предотвратить выполнение действий, схожих с приведенными ниже, из клиентского кода:</span><span class="sxs-lookup"><span data-stu-id="9cac5-112">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 <span data-ttu-id="9cac5-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9cac5-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span></span>  
  
 <span data-ttu-id="9cac5-114">Несмотря на то, что объединение строк `ints` в единый объект <xref:System.Collections.ArrayList> полностью приемлемо, а при создании разнородной коллекции нередко выполняется намеренно, в большинстве случаев это повлечет за собой ошибку программирования, которая может быть выявлена только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9cac5-114">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="9cac5-115">В версиях 1.0 и 1.1 языка C# исключить опасность, связанную с использованием обобщенного кода классов коллекций из библиотеки базовых классов платформы .NET Framework, можно было только путем написания собственных коллекций нужного типа.</span><span class="sxs-lookup"><span data-stu-id="9cac5-115">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="9cac5-116">Естественно, из-за невозможности использовать такой класс для работы с несколькими типами данных утрачивались преимущества обобщения, поскольку в этом случае требовалось создавать отдельный класс для каждого хранящегося типа.</span><span class="sxs-lookup"><span data-stu-id="9cac5-116">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="9cac5-117">Для <xref:System.Collections.ArrayList> и схожих с ним классов было необходимо, чтобы в клиентском коде для каждого экземпляра задавался конкретный тип данных, который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="9cac5-117">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="9cac5-118">Это помогло бы исключить необходимость в приведении с повышением к типу `T:System.Object` и позволило бы обеспечить проверку типов компилятором.</span><span class="sxs-lookup"><span data-stu-id="9cac5-118">That would eliminate the need for the upcast to `T:System.Object` and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="9cac5-119">Другими словами, для <xref:System.Collections.ArrayList> требуется параметр типа.</span><span class="sxs-lookup"><span data-stu-id="9cac5-119">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="9cac5-120">Именно с этой целью были реализованы универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9cac5-120">That is exactly what generics provide.</span></span> <span data-ttu-id="9cac5-121">В универсальной коллекции <xref:System.Collections.Generic.List%601> в пространстве имен `N:System.Collections.Generic` та же операция добавления элементов в коллекцию выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9cac5-121">In the generic <xref:System.Collections.Generic.List%601> collection, in the `N:System.Collections.Generic` namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 <span data-ttu-id="9cac5-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9cac5-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span></span>  
  
 <span data-ttu-id="9cac5-123">В клиентском коде в <xref:System.Collections.Generic.List%601> по сравнению с <xref:System.Collections.ArrayList> добавлен только аргумент типа для объявления и создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9cac5-123">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="9cac5-124">После этого незначительного усложнения кода стало возможным создание списка, который не только безопаснее <xref:System.Collections.ArrayList>, но и обрабатывается значительно быстрее его, особенно если его элементы представляют собой типы значений.</span><span class="sxs-lookup"><span data-stu-id="9cac5-124">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cac5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9cac5-125">See Also</span></span>  
 <span data-ttu-id="9cac5-126"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="9cac5-126"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="9cac5-127">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9cac5-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9cac5-128">[Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="9cac5-128">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="9cac5-129">[Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span><span class="sxs-lookup"><span data-stu-id="9cac5-129">[Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span></span>  
 [<span data-ttu-id="9cac5-130">Рекомендации по работе с коллекциями</span><span class="sxs-lookup"><span data-stu-id="9cac5-130">Collections Best Practices</span></span>](http://go.microsoft.com/fwlink/?LinkId=112403)

