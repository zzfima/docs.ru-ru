---
title: Сравнение и сортировка в коллекциях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1a5fa5113afdfb94a0b035b83cb59946d0970c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664580"
---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="004b5-102">Сравнение и сортировка в коллекциях</span><span class="sxs-lookup"><span data-stu-id="004b5-102">Comparisons and Sorts Within Collections</span></span>
<span data-ttu-id="004b5-103">Классы <xref:System.Collections> выполняют сравнения почти во всех процессах управления коллекциями — будь то поиск элемента для удаления или возвращение значения пары "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="004b5-103">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>  
  
 <span data-ttu-id="004b5-104">В коллекциях обычно используется компаратор проверки на равенство и (или) компаратор упорядочения.</span><span class="sxs-lookup"><span data-stu-id="004b5-104">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="004b5-105">Для сравнения используются две конструкции.</span><span class="sxs-lookup"><span data-stu-id="004b5-105">Two constructs are used for comparisons.</span></span>  
  
<a name="BKMK_Checkingforequality"></a>   
## <a name="checking-for-equality"></a><span data-ttu-id="004b5-106">Проверка на равенство</span><span class="sxs-lookup"><span data-stu-id="004b5-106">Checking for equality</span></span>  
 <span data-ttu-id="004b5-107">Такие методы, как `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>и `Remove` , используют компаратор проверки на равенство для элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="004b5-107">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="004b5-108">Если коллекция является универсальной, то элементы проверяются на равенство согласно следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="004b5-108">If the collection is generic, than items are compared for equality according to the following guidelines:</span></span>  
  
- <span data-ttu-id="004b5-109">Если тип T реализует универсальный интерфейс <xref:System.IEquatable%601> , компаратором проверки на равенство является метод <xref:System.IEquatable%601.Equals%2A> этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="004b5-109">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>  
  
- <span data-ttu-id="004b5-110">Если тип T не реализует <xref:System.IEquatable%601>, используется <xref:System.Object.Equals%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="004b5-110">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=nameWithType> is used.</span></span>  
  
 <span data-ttu-id="004b5-111">Кроме того, некоторые перегрузки конструктора для коллекций словаря принимают реализацию <xref:System.Collections.Generic.IEqualityComparer%601> , которая используется для сравнения ключей на равенство.</span><span class="sxs-lookup"><span data-stu-id="004b5-111">In addition, Some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="004b5-112">Пример см. в конструкторе <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="004b5-112">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=nameWithType> constructor.</span></span>  
  
<a name="BKMK_Determiningsortorder"></a>   
## <a name="determining-sort-order"></a><span data-ttu-id="004b5-113">Определение порядка сортировки</span><span class="sxs-lookup"><span data-stu-id="004b5-113">Determining sort order</span></span>  
 <span data-ttu-id="004b5-114">Такие методы, как `BinarySearch` и `Sort` , используют компаратор упорядочения для элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="004b5-114">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="004b5-115">Сравнение может проводиться между элементами коллекции или между элементом и заданным значением.</span><span class="sxs-lookup"><span data-stu-id="004b5-115">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="004b5-116">В процессе сравнения объектов существует понятие `default comparer` и `explicit comparer`.</span><span class="sxs-lookup"><span data-stu-id="004b5-116">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>  
  
 <span data-ttu-id="004b5-117">Для реализации интерфейса **IComparable** компаратор по умолчанию использует по крайней мере один из сравниваемых объектов.</span><span class="sxs-lookup"><span data-stu-id="004b5-117">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="004b5-118">Интерфейс **IComparable** рекомендуется реализовать во всех классах, используемых в качестве значений в коллекциях списков или в качестве ключей в коллекциях словарей.</span><span class="sxs-lookup"><span data-stu-id="004b5-118">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="004b5-119">В универсальной коллекции сравнение на равенство определяется в соответствии со следующими правилами.</span><span class="sxs-lookup"><span data-stu-id="004b5-119">For a generic collection, equality comparison is determined according to the following:</span></span>  
  
- <span data-ttu-id="004b5-120">Если тип T реализует универсальный интерфейс <xref:System.IComparable%601?displayProperty=nameWithType> , компаратором по умолчанию является метод <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="004b5-120">If type T implements the <xref:System.IComparable%601?displayProperty=nameWithType> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> method of that interface</span></span>  
  
- <span data-ttu-id="004b5-121">Если тип T реализует неуниверсальный интерфейс <xref:System.IComparable?displayProperty=nameWithType> , компаратором по умолчанию является метод <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="004b5-121">If type T implements the non-generic <xref:System.IComparable?displayProperty=nameWithType> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> method of that interface.</span></span>  
  
- <span data-ttu-id="004b5-122">Если тип T не реализует никакого интерфейса, компаратор по умолчанию отсутствует, а компаратор или делегат сравнения должен быть предоставлен явно.</span><span class="sxs-lookup"><span data-stu-id="004b5-122">If type T doesn’t implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>  
  
 <span data-ttu-id="004b5-123">Для осуществления явных сравнений некоторые методы принимают реализацию **IComparer** в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="004b5-123">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="004b5-124">Например, метод <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> принимает реализацию <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="004b5-124">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation.</span></span>  
  
 <span data-ttu-id="004b5-125">Текущее значение языка и региональных параметров системы может влиять на сравнения и сортировки в рамках коллекции.</span><span class="sxs-lookup"><span data-stu-id="004b5-125">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="004b5-126">По умолчанию сравнения и сортировки в классах **Collections** зависят от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="004b5-126">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="004b5-127">Чтобы игнорировать параметр языка и региональные параметры и получить согласованные результаты сравнения и сортировки, используйте <xref:System.Globalization.CultureInfo.InvariantCulture%2A> с перегрузками элементов, принимающими <xref:System.Globalization.CultureInfo>.</span><span class="sxs-lookup"><span data-stu-id="004b5-127">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="004b5-128">Дополнительные сведения см. в разделах [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) и [Performing Culture-Insensitive String Operations in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="004b5-128">For more information, see [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>  
  
<a name="BKMK_Equalityandsortexample"></a>   
## <a name="equality-and-sort-example"></a><span data-ttu-id="004b5-129">Пример сортировки и проверки на равенство</span><span class="sxs-lookup"><span data-stu-id="004b5-129">Equality and sort example</span></span>  
 <span data-ttu-id="004b5-130">В следующем примере демонстрируется реализация <xref:System.IEquatable%601> и <xref:System.IComparable%601> в простом бизнес-объекте.</span><span class="sxs-lookup"><span data-stu-id="004b5-130">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="004b5-131">Кроме того, когда объект сохраняется в списке и сортируется, вы увидите, что вызов метода <xref:System.Collections.Generic.List%601.Sort> приведет к использованию компаратора по умолчанию для типа `Part` , а метод <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> будет реализован с помощью анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="004b5-131">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>  
  
 [!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
 [!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="004b5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="004b5-132">See also</span></span>

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
