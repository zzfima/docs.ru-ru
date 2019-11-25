---
title: Руководство по программированию на C#. Инициализаторы объектов и набора
ms.custom: seodec18
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 837be04208d438f15b4cc7c7124a47ef6c038cb2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455439"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="de813-102">Инициализаторы объектов и коллекций (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="de813-102">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="de813-103">C# позволяет создать экземпляр объекта или коллекции и выполнять присваивания его членов в одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="de813-103">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="de813-104">Инициализаторы объектов</span><span class="sxs-lookup"><span data-stu-id="de813-104">Object initializers</span></span>

<span data-ttu-id="de813-105">Инициализаторы объектов позволяют присваивать значения всем доступным полям и свойствам объекта во время создания без вызова конструктора, за которым следуют строки операторов присваивания.</span><span class="sxs-lookup"><span data-stu-id="de813-105">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="de813-106">Синтаксис инициализатора объекта позволяет задавать аргументы конструктора или опускать их (и синтаксис в скобках).</span><span class="sxs-lookup"><span data-stu-id="de813-106">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="de813-107">В приведенном ниже примере демонстрируется использование инициализатора объекта с именованным типом `Cat` и вызов конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="de813-107">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="de813-108">Обратите внимание на использование в классе `Cat` автоматически внедренных свойств.</span><span class="sxs-lookup"><span data-stu-id="de813-108">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="de813-109">Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="de813-109">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
<span data-ttu-id="de813-110">Синтаксис инициализаторов объектов позволяет создать экземпляр, а затем присваивает созданный объект, включая назначенные ему свойства, переменной в назначении.</span><span class="sxs-lookup"><span data-stu-id="de813-110">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="de813-111">Начиная с C# 6 инициализаторы объектов могут задавать индексаторы, кроме назначения полей и свойств.</span><span class="sxs-lookup"><span data-stu-id="de813-111">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="de813-112">Рассмотрим следующий базовый класс `Matrix`:</span><span class="sxs-lookup"><span data-stu-id="de813-112">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="de813-113">Можно инициализировать единичную матрицу следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="de813-113">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="de813-114">Любой доступный индексатор, который содержит доступный метод задания, можно использовать как одно из выражений в инициализаторе объекта независимо от количества или типов аргументов.</span><span class="sxs-lookup"><span data-stu-id="de813-114">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="de813-115">Аргументы индекса формируют левую часть присваивания, а значение стоит в его правой части.</span><span class="sxs-lookup"><span data-stu-id="de813-115">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="de813-116">Например, все нижеприведенные конструкции допустимы, если `IndexersExample` имеет соответствующие индексаторы:</span><span class="sxs-lookup"><span data-stu-id="de813-116">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="de813-117">Для компиляции приведенного выше кода тип `IndexersExample` должен иметь следующие члены:</span><span class="sxs-lookup"><span data-stu-id="de813-117">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="de813-118">Инициализаторы объектов с анонимными типами</span><span class="sxs-lookup"><span data-stu-id="de813-118">Object Initializers with anonymous types</span></span>

<span data-ttu-id="de813-119">Хотя инициализаторы объектов можно использовать в любом контексте, они особенно полезны в выражениях запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de813-119">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="de813-120">В выражениях запросов часто используются [анонимные типы](./anonymous-types.md), которые можно инициализировать только с помощью инициализаторов объектов, как показано в приведенном ниже объявлении.</span><span class="sxs-lookup"><span data-stu-id="de813-120">Query expressions make frequent use of [anonymous types](./anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="de813-121">Анонимные типы позволяют предложению `select` в выражении запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] преобразовывать объекты исходной последовательности в объекты, значение и форма которых могут отличаться от исходных.</span><span class="sxs-lookup"><span data-stu-id="de813-121">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="de813-122">Это бывает полезно, если требуется сохранить лишь часть информации от каждого объекта последовательности.</span><span class="sxs-lookup"><span data-stu-id="de813-122">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="de813-123">В приведенном ниже примере предполагается, что у объекта продукта (`p`) имеется множество полей и методов, и требуется создать последовательность объектов, содержащую только имя продукта и его цену.</span><span class="sxs-lookup"><span data-stu-id="de813-123">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="de813-124">При выполнении этого запроса переменная `productInfos` будет содержать последовательность объектов, доступных в операторе `foreach`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="de813-124">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="de813-125">Каждый объект нового анонимного типа содержит два общедоступных свойства, имеющих те же имена, что и у свойств или полей исходного объекта.</span><span class="sxs-lookup"><span data-stu-id="de813-125">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="de813-126">Кроме того, при создании анонимного типа можно переименовать поле; в следующем примере выполняется переименование поля `UnitPrice` в `Price`.</span><span class="sxs-lookup"><span data-stu-id="de813-126">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="de813-127">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="de813-127">Collection initializers</span></span>

<span data-ttu-id="de813-128">Инициализаторы коллекций позволяют задавать один или несколько инициализаторов элементов при инициализации типа коллекции, который реализует интерфейс <xref:System.Collections.IEnumerable> и включает `Add` с соответствующей сигнатурой как метод экземпляра или метод расширения.</span><span class="sxs-lookup"><span data-stu-id="de813-128">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="de813-129">Инициализаторами элементов могут быть простые значения, выражения и инициализаторы объектов.</span><span class="sxs-lookup"><span data-stu-id="de813-129">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="de813-130">При использовании инициализатора коллекции не требуется указывать несколько вызовов; эти вызовы добавляет компилятор.</span><span class="sxs-lookup"><span data-stu-id="de813-130">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="de813-131">Ниже приведен пример двух простых инициализаторов коллекций.</span><span class="sxs-lookup"><span data-stu-id="de813-131">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="de813-132">В следующем инициализаторе коллекции используются инициализаторы объектов класса `Cat`, определенного в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="de813-132">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="de813-133">Обратите внимание, что инициализаторы отдельных объектов заключены в скобки и разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="de813-133">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="de813-134">В качестве элемента инициализатора коллекции можно указать значение [null](../../language-reference/keywords/null.md), если метод `Add` коллекции допускает это.</span><span class="sxs-lookup"><span data-stu-id="de813-134">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="de813-135">Можно указать индексированные элементы, если коллекция поддерживает индексирование чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="de813-135">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="de813-136">В предыдущем примере создается код, который вызывает <xref:System.Collections.Generic.Dictionary%602.Item(%600)> для задания значений.</span><span class="sxs-lookup"><span data-stu-id="de813-136">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="de813-137">В версиях C# ниже 6 можно было инициализировать словари и другие ассоциативные контейнеры, используя указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="de813-137">Before C# 6, you could initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="de813-138">Обратите внимание, что вместо синтаксиса индексатора с круглыми скобками и присваиванием он использует объект с несколькими значениями:</span><span class="sxs-lookup"><span data-stu-id="de813-138">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="de813-139">В этом примере инициализатор вызывает <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> для добавления трех элементов в словарь.</span><span class="sxs-lookup"><span data-stu-id="de813-139">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="de813-140">Эти два разных способа инициализации ассоциативных коллекций немного отличаются из-за вызовов методов, которые создает компилятор.</span><span class="sxs-lookup"><span data-stu-id="de813-140">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="de813-141">Оба варианта могут работать с классом `Dictionary`.</span><span class="sxs-lookup"><span data-stu-id="de813-141">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="de813-142">Другие типы могут поддерживать только один из них в зависимости от своего открытого API.</span><span class="sxs-lookup"><span data-stu-id="de813-142">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="de813-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="de813-143">Examples</span></span>

<span data-ttu-id="de813-144">В следующем примере объединяются понятия инициализаторов коллекций и объектов.</span><span class="sxs-lookup"><span data-stu-id="de813-144">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="de813-145">В примере ниже представлен объект, в котором реализован интерфейс <xref:System.Collections.IEnumerable>. Он содержит метод `Add` с несколькими параметрами, позволяющими использовать инициализаторы коллекций с несколькими элементами для каждого пункта списка, который соответствует сигнатуре метода `Add`.</span><span class="sxs-lookup"><span data-stu-id="de813-145">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="de813-146">В методах `Add` можно использовать ключевое слово `params`, чтобы принимать переменное число аргументов, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="de813-146">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="de813-147">Здесь также демонстрируется пользовательская реализация индексатора, которая также применяется для инициализации коллекции с помощью индексов.</span><span class="sxs-lookup"><span data-stu-id="de813-147">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="de813-148">См. также</span><span class="sxs-lookup"><span data-stu-id="de813-148">See also</span></span>

- [<span data-ttu-id="de813-149">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="de813-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="de813-150">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="de813-150">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="de813-151">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="de813-151">Anonymous Types</span></span>](anonymous-types.md)
