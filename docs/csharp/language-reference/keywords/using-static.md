---
title: Директива using static (справочник по C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5838bede475cf2ad1b72518770241e86206a06bb
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="ea378-102">Директива using static (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ea378-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="ea378-103">Директива `using static` обозначает тип, доступ к статическим членам которого можно получить, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="ea378-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="ea378-104">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ea378-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="ea378-105">здесь *полное имя типа* — это имя типа, на статические члены которого можно ссылаться, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="ea378-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="ea378-106">Если полное имя (полное имя пространства имен вместе с именем типа) не указано, C# создает ошибку компилятора CS0246: "Тип или пространство имен '<type-name>' не найдены".</span><span class="sxs-lookup"><span data-stu-id="ea378-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="ea378-107">Директива `using static` применяется к каждому типу, у которого есть статические члены, даже если при этом у него также имеются члены экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ea378-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="ea378-108">При этом для вызова членов экземпляров можно использовать только экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="ea378-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="ea378-109">Директива `using static` была представлена в C# версии 6.</span><span class="sxs-lookup"><span data-stu-id="ea378-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea378-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea378-110">Remarks</span></span>
 
<span data-ttu-id="ea378-111">Обычно при вызове статического члена необходимо указать имя типа и имя нужного члена.</span><span class="sxs-lookup"><span data-stu-id="ea378-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="ea378-112">Повторный ввод одного и того же имени типа для вызова относящихся к нему элементов может сделать код слишком длинным и сложным.</span><span class="sxs-lookup"><span data-stu-id="ea378-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="ea378-113">Например, следующее определение класса `Circle` ссылается на ряд членов класса <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="ea378-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>
  
[!code-csharp[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="ea378-114">Поскольку явно ссылаться на класс <xref:System.Math> при каждой ссылке на член не требуется, директива `using static` создает гораздо более понятный код:</span><span class="sxs-lookup"><span data-stu-id="ea378-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="ea378-115">`using static` импортирует только доступные статические члены и вложенные типы, объявленные в указанном типе.</span><span class="sxs-lookup"><span data-stu-id="ea378-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="ea378-116">Унаследованные члены не импортируются.</span><span class="sxs-lookup"><span data-stu-id="ea378-116">Inherited members are not imported.</span></span>  <span data-ttu-id="ea378-117">Можно импортировать из любого именованного типа с помощью директивы using static, включая модули Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ea378-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="ea378-118">Если функции F# верхнего уровня отображаются в метаданных как статические члены именованного типа, имя которого является допустимым идентификатором C#, то эти функции F# можно импортировать.</span><span class="sxs-lookup"><span data-stu-id="ea378-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="ea378-119">`using static` делает методы расширения, объявленные в указанном типе, доступными для поиска метода расширения.</span><span class="sxs-lookup"><span data-stu-id="ea378-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="ea378-120">Тем не менее имена методов расширения не импортируются в область для неквалифицированной ссылки в коде.</span><span class="sxs-lookup"><span data-stu-id="ea378-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="ea378-121">Методы с тем же именем, импортированные из различных типов разными директивами `using static` в том же блоке компиляции или пространстве имен, формируют группу методов.</span><span class="sxs-lookup"><span data-stu-id="ea378-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="ea378-122">Разрешение перегрузки в этих группах методов соответствует обычным правилам языка C#.</span><span class="sxs-lookup"><span data-stu-id="ea378-122">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea378-123">Пример</span><span class="sxs-lookup"><span data-stu-id="ea378-123">Example</span></span>

<span data-ttu-id="ea378-124">В следующем примере директива `using static` используется для того, чтобы доступ к статическим членам классов <xref:System.Console>, <xref:System.Math> и <xref:System.String> можно было получать, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="ea378-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="ea378-125">В этом примере директива `using static` может также применяться к типу <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="ea378-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="ea378-126">Это будет появилась возможность вызова <xref:System.Double.TryParse(System.String,System.Double@)> метод без указания имени типа.</span><span class="sxs-lookup"><span data-stu-id="ea378-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="ea378-127">При этом код становится менее понятным, поскольку появляется необходимость проверять операторы `using static` и определять, какой метод числового типа `TryParse` вызывается.</span><span class="sxs-lookup"><span data-stu-id="ea378-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea378-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ea378-128">See also</span></span>

<span data-ttu-id="ea378-129">[Директива using](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="ea378-129">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="ea378-130">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ea378-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="ea378-131">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ea378-131">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="ea378-132">[Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="ea378-132">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="ea378-133">[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="ea378-133">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="ea378-134">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="ea378-134">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   
