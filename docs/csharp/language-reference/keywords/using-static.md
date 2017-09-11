---
title: "Директива using static (справочник по C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: b7d69d0262ba6f450e2cc0d5b30692bba181f9d9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="c2ad9-102">Директива using static (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c2ad9-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="c2ad9-103">Директива `using static` обозначает тип, доступ к статическим членам которого можно получить, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="c2ad9-104">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2ad9-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="c2ad9-105">здесь *полное имя типа* — это имя типа, на статические члены которого можно ссылаться, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="c2ad9-106">Если полное имя (полное имя пространства имен вместе с именем типа) не указано, C# создает ошибку компилятора CS0246: "Тип или пространство имен '<type-name>' не найдены".</span><span class="sxs-lookup"><span data-stu-id="c2ad9-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="c2ad9-107">Директива `using static` применяется к каждому типу, у которого есть статические члены, даже если при этом у него также имеются члены экземпляров.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="c2ad9-108">При этом для вызова членов экземпляров можно использовать только экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="c2ad9-109">Директива `using static` была представлена в C# версии 6.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2ad9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2ad9-110">Remarks</span></span>
 
<span data-ttu-id="c2ad9-111">Обычно при вызове статического члена необходимо указать имя типа и имя нужного члена.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="c2ad9-112">Повторный ввод одного и того же имени типа для вызова относящихся к нему элементов может сделать код слишком длинным и сложным.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="c2ad9-113">Например, следующее определение класса `Circle` ссылается на ряд членов класса @System.Math.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-113">For example, the following definition of a `Circle` class references a number of members of the @System.Math class.</span></span>
  
<span data-ttu-id="c2ad9-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2ad9-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span></span>

<span data-ttu-id="c2ad9-115">Поскольку явно ссылаться на класс @System.Math при каждой ссылке на член не требуется, директива `using static` создает гораздо более понятный код:</span><span class="sxs-lookup"><span data-stu-id="c2ad9-115">By eliminating the need to explicitly reference the @System.Math class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

<span data-ttu-id="c2ad9-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2ad9-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span></span>

<span data-ttu-id="c2ad9-117">`using static` импортирует только доступные статические члены и вложенные типы, объявленные в указанном типе.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-117">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="c2ad9-118">Унаследованные члены не импортируются.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-118">Inherited members are not imported.</span></span>  <span data-ttu-id="c2ad9-119">Можно импортировать из любого именованного типа с помощью директивы using static, включая модули Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-119">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="c2ad9-120">Если функции F# верхнего уровня отображаются в метаданных как статические члены именованного типа, имя которого является допустимым идентификатором C#, то эти функции F# можно импортировать.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-120">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="c2ad9-121">`using static` делает методы расширения, объявленные в указанном типе, доступными для поиска метода расширения.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-121">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="c2ad9-122">Тем не менее имена методов расширения не импортируются в область для неквалифицированной ссылки в коде.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-122">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="c2ad9-123">Методы с тем же именем, импортированные из различных типов разными директивами `using static` в том же блоке компиляции или пространстве имен, формируют группу методов.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-123">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="c2ad9-124">Разрешение перегрузки в этих группах методов соответствует обычным правилам языка C#.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-124">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2ad9-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c2ad9-125">Example</span></span>

<span data-ttu-id="c2ad9-126">В следующем примере директива `using static` используется для того, чтобы доступ к статическим членам классов @System.Console, @System.Math и @System.String можно было получать, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-126">The following example uses the `using static` directive to make the static members of the @System.Console, @System.Math, and @System.String classes available without having to specify their type name.</span></span>

<span data-ttu-id="c2ad9-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c2ad9-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span></span>

<span data-ttu-id="c2ad9-128">В этом примере директива `using static` может также применяться к типу @System.Double.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-128">In the example, the `using static` directive could also have been applied to the @System.Double type.</span></span> <span data-ttu-id="c2ad9-129">В этом случае вызвать метод @System.Double.TryParse(System.String,System.Double@), не указав имя типа, было бы невозможно.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-129">This would have made it possible to call the @System.Double.TryParse(System.String,System.Double@) method without specifying a type name.</span></span> <span data-ttu-id="c2ad9-130">При этом код становится менее понятным, поскольку появляется необходимость проверять операторы `using static` и определять, какой метод числового типа `TryParse` вызывается.</span><span class="sxs-lookup"><span data-stu-id="c2ad9-130">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2ad9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c2ad9-131">See also</span></span>

<span data-ttu-id="c2ad9-132">[Директива using](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="c2ad9-132">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="c2ad9-133">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2ad9-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="c2ad9-134">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2ad9-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="c2ad9-135">[Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="c2ad9-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="c2ad9-136">[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="c2ad9-136">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="c2ad9-137">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="c2ad9-137">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   

