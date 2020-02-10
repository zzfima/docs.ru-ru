---
title: Справочник по C#. Директива using
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 4f7ddad8c3dc12391ef6bf345a73ebb384400b38
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093153"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="e503f-102">Директива using (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e503f-102">using directive (C# Reference)</span></span>

<span data-ttu-id="e503f-103">Директива `using` используется в следующих трех целях.</span><span class="sxs-lookup"><span data-stu-id="e503f-103">The `using` directive has three uses:</span></span>

- <span data-ttu-id="e503f-104">Для разрешения использования типов в пространстве имен, чтобы не нужно было квалифицировать использование типа в этом пространстве имен:</span><span class="sxs-lookup"><span data-stu-id="e503f-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>

    ```csharp
    using System.Text;
    ```

- <span data-ttu-id="e503f-105">Для разрешения доступа к статическим членам и вложенным типам без необходимости квалифицировать доступ с помощью имени типа.</span><span class="sxs-lookup"><span data-stu-id="e503f-105">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span>

    ```csharp
    using static System.Math;
    ```

    <span data-ttu-id="e503f-106">Дополнительные сведения см. в разделе [Директива using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="e503f-106">For more information, see the [using static directive](using-static.md).</span></span>

- <span data-ttu-id="e503f-107">Чтобы создать псевдоним для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="e503f-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="e503f-108">Это называется *директивой using static*.</span><span class="sxs-lookup"><span data-stu-id="e503f-108">This is called a *using alias directive*.</span></span>

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

<span data-ttu-id="e503f-109">Ключевое слово `using` также используется для создания *операторов using*, которые помогают обеспечить правильную обработку объектов <xref:System.IDisposable>, таких как файлы и шрифты.</span><span class="sxs-lookup"><span data-stu-id="e503f-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="e503f-110">Дополнительные сведения см. в разделе [Оператор using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e503f-110">See [using Statement](using-statement.md) for more information.</span></span>

## <a name="using-static-type"></a><span data-ttu-id="e503f-111">Использование статического типа</span><span class="sxs-lookup"><span data-stu-id="e503f-111">Using static type</span></span>

<span data-ttu-id="e503f-112">Вы можете обращаться к статическим членам типа без необходимости квалификации доступа с помощью имени типа:</span><span class="sxs-lookup"><span data-stu-id="e503f-112">You can access static members of a type without having to qualify the access with the type name:</span></span>

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a><span data-ttu-id="e503f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e503f-113">Remarks</span></span>

<span data-ttu-id="e503f-114">Область директивы `using` ограничена файлом, в котором она находится.</span><span class="sxs-lookup"><span data-stu-id="e503f-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>

<span data-ttu-id="e503f-115">Директива `using` может отображаться:</span><span class="sxs-lookup"><span data-stu-id="e503f-115">The `using` directive can appear:</span></span>

- <span data-ttu-id="e503f-116">В начале файла исходного кода перед определением пространств имен и типов.</span><span class="sxs-lookup"><span data-stu-id="e503f-116">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="e503f-117">В пространстве имен перед любыми пространствами имен и типами, объявленными в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="e503f-117">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="e503f-118">В противном случае возникнет ошибка компилятора [CS1529](../../misc/cs1529.md).</span><span class="sxs-lookup"><span data-stu-id="e503f-118">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>

<span data-ttu-id="e503f-119">Создайте директиву псевдонима `using`, чтобы упростить квалификацию идентификатора для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="e503f-119">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="e503f-120">Во всех директивах `using` следует использовать полное пространство имен или тип независимо от того, какие директивы `using` находятся перед ней.</span><span class="sxs-lookup"><span data-stu-id="e503f-120">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="e503f-121">В объявлении директивы `using` не может использоваться псевдоним `using`.</span><span class="sxs-lookup"><span data-stu-id="e503f-121">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="e503f-122">Например, следующий код вызовет ошибку компиляции:</span><span class="sxs-lookup"><span data-stu-id="e503f-122">For example, the following generates a compiler error:</span></span>

```csharp
using s = System.Text;
using s.RegularExpressions; // Generates a compiler error.
```

<span data-ttu-id="e503f-123">Создайте директиву `using`, чтобы использовать типы в пространстве имен без необходимости указания этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e503f-123">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="e503f-124">Директива `using` не предоставляет доступ к пространствам имен, вложенным в указанное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="e503f-124">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>

<span data-ttu-id="e503f-125">Пространства имен делятся на две категории: пользовательские и системные.</span><span class="sxs-lookup"><span data-stu-id="e503f-125">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="e503f-126">Пользовательские пространства имен задаются в вашем коде.</span><span class="sxs-lookup"><span data-stu-id="e503f-126">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="e503f-127">Список системных пространств имен см. в разделе [Браузер API .NET](../../../../api/index.md).</span><span class="sxs-lookup"><span data-stu-id="e503f-127">For a list of the system-defined namespaces, see [.NET API Browser](../../../../api/index.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="e503f-128">Пример 1</span><span class="sxs-lookup"><span data-stu-id="e503f-128">Example 1</span></span>

<span data-ttu-id="e503f-129">В следующем примере показано, как задать и использовать псевдоним `using` для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e503f-129">The following example shows how to define and use a `using` alias for a namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

<span data-ttu-id="e503f-130">Псевдоним using не может иметь открытый универсальный тип с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="e503f-130">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="e503f-131">Например, нельзя создать псевдоним using для `List<T>`, но можно создать его для `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="e503f-131">For example, you cannot create a using alias for a `List<T>`, but you can create one for a `List<int>`.</span></span>

## <a name="example-2"></a><span data-ttu-id="e503f-132">Пример 2</span><span class="sxs-lookup"><span data-stu-id="e503f-132">Example 2</span></span>

<span data-ttu-id="e503f-133">В следующем примере показано, как задать директиву `using` и псевдоним `using` для класса.</span><span class="sxs-lookup"><span data-stu-id="e503f-133">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="e503f-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e503f-134">C# language specification</span></span>

<span data-ttu-id="e503f-135">Дополнительные сведения см. в разделе [Директивы using](~/_csharplang/spec/namespaces.md#using-directives) в статье [Спецификация языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="e503f-135">For more information, see [Using directives](~/_csharplang/spec/namespaces.md#using-directives) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="e503f-136">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="e503f-136">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="e503f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e503f-137">See also</span></span>

- [<span data-ttu-id="e503f-138">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e503f-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e503f-139">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e503f-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e503f-140">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="e503f-140">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="e503f-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e503f-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e503f-142">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="e503f-142">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
- [<span data-ttu-id="e503f-143">Оператор using</span><span class="sxs-lookup"><span data-stu-id="e503f-143">using Statement</span></span>](using-statement.md)
