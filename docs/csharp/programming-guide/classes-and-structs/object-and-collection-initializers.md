---
title: Инициализаторы объектов и коллекций (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 9986a91b18c536773f4ca20b71c54588c3e95f32
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43476135"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="116e3-102">Инициализаторы объектов и коллекций (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="116e3-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="116e3-103">Инициализаторы объектов позволяют присваивать значения всем доступным полям и свойствам объекта во время создания без вызова конструктора, за которым следуют строки операторов присваивания.</span><span class="sxs-lookup"><span data-stu-id="116e3-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="116e3-104">Синтаксис инициализатора объекта позволяет задавать аргументы конструктора или опускать их (и синтаксис в скобках).</span><span class="sxs-lookup"><span data-stu-id="116e3-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="116e3-105">В следующем примере показаны использование инициализатора объекта с именованным типом `Cat` и вызов конструктора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="116e3-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="116e3-106">Обратите внимание на использование в классе `Cat` автоматически внедренных свойств.</span><span class="sxs-lookup"><span data-stu-id="116e3-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="116e3-107">Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="116e3-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="116e3-108">Синтаксис инициализаторов объектов позволяет создать экземпляр, а затем присваивает созданный объект, включая назначенные ему свойства, переменной в назначении.</span><span class="sxs-lookup"><span data-stu-id="116e3-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="116e3-109">Инициализаторы объектов с анонимными типами</span><span class="sxs-lookup"><span data-stu-id="116e3-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="116e3-110">Хотя инициализаторы объектов можно использовать в любом контексте, они особенно полезны в выражениях запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116e3-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="116e3-111">В выражениях запросов часто используются [анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), которые можно инициализировать только с помощью инициализаторов объектов, как показано в приведенном ниже объявлении.</span><span class="sxs-lookup"><span data-stu-id="116e3-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="116e3-112">Анонимные типы позволяют предложению `select` в выражении запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] преобразовывать объекты исходной последовательности в объекты, значение и форма которых могут отличаться от исходных.</span><span class="sxs-lookup"><span data-stu-id="116e3-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="116e3-113">Это бывает полезно, если требуется сохранить лишь часть информации от каждого объекта последовательности.</span><span class="sxs-lookup"><span data-stu-id="116e3-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="116e3-114">В приведенном ниже примере предполагается, что у объекта продукта (`p`) имеется множество полей и методов, и требуется создать последовательность объектов, содержащую только имя продукта и его цену.</span><span class="sxs-lookup"><span data-stu-id="116e3-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="116e3-115">При выполнении этого запроса переменная `productInfos` будет содержать последовательность объектов, доступных в операторе `foreach`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="116e3-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="116e3-116">Каждый объект нового анонимного типа содержит два общедоступных свойства, имеющих те же имена, что и у свойств или полей исходного объекта.</span><span class="sxs-lookup"><span data-stu-id="116e3-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="116e3-117">Кроме того, при создании анонимного типа можно переименовать поле; в следующем примере выполняется переименование поля `UnitPrice` в `Price`.</span><span class="sxs-lookup"><span data-stu-id="116e3-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="collection-initializers"></a><span data-ttu-id="116e3-118">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="116e3-118">Collection initializers</span></span>  
 <span data-ttu-id="116e3-119">Инициализаторы коллекций позволяют задавать один или несколько инициализаторов элементов при инициализации типа коллекции, который реализует интерфейс <xref:System.Collections.IEnumerable> и включает `Add` с соответствующей сигнатурой как метод экземпляра или метод расширения.</span><span class="sxs-lookup"><span data-stu-id="116e3-119">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="116e3-120">Инициализаторами элементов могут быть простые значения, выражения и инициализаторы объектов.</span><span class="sxs-lookup"><span data-stu-id="116e3-120">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="116e3-121">При использовании инициализатора коллекции не требуется указывать в исходном коде несколько вызовов метода `Add` класса; эти вызовы добавляет компилятор.</span><span class="sxs-lookup"><span data-stu-id="116e3-121">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="116e3-122">Ниже приведены два примера простых инициализаторов коллекций.</span><span class="sxs-lookup"><span data-stu-id="116e3-122">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="116e3-123">В следующем инициализаторе коллекции используются инициализаторы объектов класса `Cat`, определенного в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="116e3-123">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="116e3-124">Обратите внимание, что инициализаторы отдельных объектов заключены в скобки и разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="116e3-124">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="116e3-125">В качестве элемента инициализатора коллекции можно указать значение [null](../../../csharp/language-reference/keywords/null.md), если метод `Add` коллекции допускает это.</span><span class="sxs-lookup"><span data-stu-id="116e3-125">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="116e3-126">Можно указать индексированные элементы, если коллекция поддерживает индексирование.</span><span class="sxs-lookup"><span data-stu-id="116e3-126">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a><span data-ttu-id="116e3-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="116e3-127">Examples</span></span>

 <span data-ttu-id="116e3-128">В следующем примере объединяются понятия инициализаторов коллекций и объектов.</span><span class="sxs-lookup"><span data-stu-id="116e3-128">The following example combines the concepts of object and collection initializers.</span></span>

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 <span data-ttu-id="116e3-129">В примере ниже представлен объект, в котором реализован интерфейс <xref:System.Collections.IEnumerable>. Он содержит метод `Add` с несколькими параметрами, позволяющими использовать инициализаторы коллекций с несколькими элементами для каждого пункта списка, который соответствует сигнатуре метода `Add`.</span><span class="sxs-lookup"><span data-stu-id="116e3-129">Shown in the following example, an object which implements <xref:System.Collections.IEnumerable> containing an `Add` method with multiple parameters allows for collection initializers with multiple elements per item in the list corresponding to the signature of the `Add` method.</span></span> 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 <span data-ttu-id="116e3-130">В методах `Add` можно использовать ключевое слово `params`, чтобы принимать переменное число аргументов, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="116e3-130">`Add` methods can use the `params` keyword to take a variable number of arguments as shown in the following example.</span></span> <span data-ttu-id="116e3-131">Здесь демонстрируется пользовательская реализация индексатора, которая также применяется для инициализации коллекции с помощью индексов.</span><span class="sxs-lookup"><span data-stu-id="116e3-131">This example demonstrates the custom implementation of an indexer as well to initialize a collection using indexes.</span></span>
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a><span data-ttu-id="116e3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="116e3-132">See Also</span></span>  
 [<span data-ttu-id="116e3-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="116e3-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="116e3-134">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="116e3-134">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="116e3-135">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="116e3-135">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
