---
title: Справочник по C#. Директива using static
ms.date: 03/10/2017
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: 55847aceb9fdf032ba533b82ee59be53761fa2c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712953"
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="02664-102">Директива using static (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="02664-102">using static directive (C# Reference)</span></span>

<span data-ttu-id="02664-103">Директива `using static` обозначает тип, доступ к статическим членам и вложенным типам которого можно получить, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="02664-103">The `using static` directive designates a type whose static members and nested types you can access without specifying a type name.</span></span> <span data-ttu-id="02664-104">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="02664-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>;
```

<span data-ttu-id="02664-105">здесь *полное имя типа* — это имя типа, на статические члены и вложенные типы которого можно ссылаться, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="02664-105">where *fully-qualified-type-name* is the name of the type whose static members and nested types can be referenced without specifying a type name.</span></span> <span data-ttu-id="02664-106">Если полное имя (полное имя пространства имен вместе с именем типа) не указано, C# создает ошибку компилятора [CS0246](../compiler-messages/cs0246.md): "Тип или пространство имен 'type/namespace' не найдены (отсутствует директива using или ссылка сборки)".</span><span class="sxs-lookup"><span data-stu-id="02664-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error [CS0246](../compiler-messages/cs0246.md): "The type or namespace name 'type/namespace' could not be found (are you missing a using directive or an assembly reference?)".</span></span>

<span data-ttu-id="02664-107">Директива `using static` применяется к каждому типу, у которого есть статические члены (или вложенные типы), даже если при этом у него также имеются члены экземпляров.</span><span class="sxs-lookup"><span data-stu-id="02664-107">The `using static` directive applies to any type that has static members (or nested types), even if it also has instance members.</span></span> <span data-ttu-id="02664-108">При этом для вызова членов экземпляров можно использовать только экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="02664-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="02664-109">Директива `using static` была представлена в C# версии 6.</span><span class="sxs-lookup"><span data-stu-id="02664-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="02664-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="02664-110">Remarks</span></span>

<span data-ttu-id="02664-111">Обычно при вызове статического члена необходимо указать имя типа и имя нужного члена.</span><span class="sxs-lookup"><span data-stu-id="02664-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="02664-112">Повторный ввод одного и того же имени типа для вызова относящихся к нему элементов может сделать код слишком длинным и сложным.</span><span class="sxs-lookup"><span data-stu-id="02664-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="02664-113">Например, следующее определение класса `Circle` ссылается на ряд членов класса <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="02664-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="02664-114">Поскольку явно ссылаться на класс <xref:System.Math> при каждой ссылке на член не требуется, директива `using static` создает гораздо более понятный код:</span><span class="sxs-lookup"><span data-stu-id="02664-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="02664-115">`using static` импортирует только доступные статические члены и вложенные типы, объявленные в указанном типе.</span><span class="sxs-lookup"><span data-stu-id="02664-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="02664-116">Унаследованные члены не импортируются.</span><span class="sxs-lookup"><span data-stu-id="02664-116">Inherited members are not imported.</span></span>  <span data-ttu-id="02664-117">Можно импортировать из любого именованного типа с помощью директивы using static, включая модули Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="02664-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="02664-118">Если функции F# верхнего уровня отображаются в метаданных как статические члены именованного типа, имя которого является допустимым идентификатором C#, то эти функции F# можно импортировать.</span><span class="sxs-lookup"><span data-stu-id="02664-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>

 <span data-ttu-id="02664-119">`using static` делает методы расширения, объявленные в указанном типе, доступными для поиска метода расширения.</span><span class="sxs-lookup"><span data-stu-id="02664-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="02664-120">Тем не менее имена методов расширения не импортируются в область для неквалифицированной ссылки в коде.</span><span class="sxs-lookup"><span data-stu-id="02664-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>

 <span data-ttu-id="02664-121">Методы с тем же именем, импортированные из различных типов разными директивами `using static` в том же блоке компиляции или пространстве имен, формируют группу методов.</span><span class="sxs-lookup"><span data-stu-id="02664-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="02664-122">Разрешение перегрузки в этих группах методов соответствует обычным правилам языка C#.</span><span class="sxs-lookup"><span data-stu-id="02664-122">Overload resolution within these method groups follows normal C# rules.</span></span>

## <a name="example"></a><span data-ttu-id="02664-123">Пример</span><span class="sxs-lookup"><span data-stu-id="02664-123">Example</span></span>

<span data-ttu-id="02664-124">В следующем примере директива `using static` используется для того, чтобы доступ к статическим членам классов <xref:System.Console>, <xref:System.Math> и <xref:System.String> можно было получать, не указывая имя типа.</span><span class="sxs-lookup"><span data-stu-id="02664-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="02664-125">В этом примере директива `using static` может также применяться к типу <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="02664-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="02664-126">В этом случае вызвать метод <xref:System.Double.TryParse(System.String,System.Double@)>, не указав имя типа, было бы возможно.</span><span class="sxs-lookup"><span data-stu-id="02664-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="02664-127">При этом код становится менее понятным, поскольку появляется необходимость проверять операторы `using static` и определять, какой метод числового типа `TryParse` вызывается.</span><span class="sxs-lookup"><span data-stu-id="02664-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="02664-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="02664-128">See also</span></span>

- [<span data-ttu-id="02664-129">Директива using</span><span class="sxs-lookup"><span data-stu-id="02664-129">using directive</span></span>](using-directive.md)
- [<span data-ttu-id="02664-130">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="02664-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02664-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="02664-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="02664-132">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="02664-132">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="02664-133">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="02664-133">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
