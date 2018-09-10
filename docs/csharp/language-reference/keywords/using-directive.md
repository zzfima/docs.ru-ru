---
title: Директива using (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 1ed7ac49cde6792cddff898e8b9930a83598e02c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183084"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="00129-102">Директива using (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="00129-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="00129-103">Директива `using` используется в следующих трех целях.</span><span class="sxs-lookup"><span data-stu-id="00129-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="00129-104">Для разрешения использования типов в пространстве имен, чтобы не нужно было квалифицировать использование типа в этом пространстве имен:</span><span class="sxs-lookup"><span data-stu-id="00129-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="00129-105">Для разрешения доступа к статическим членам и вложенным типам без необходимости квалифицировать доступ с помощью имени типа.</span><span class="sxs-lookup"><span data-stu-id="00129-105">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="00129-106">Дополнительные сведения см. в разделе [Директива using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="00129-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="00129-107">Чтобы создать псевдоним для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="00129-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="00129-108">Это называется *директивой using static*.</span><span class="sxs-lookup"><span data-stu-id="00129-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="00129-109">Ключевое слово `using` также используется для создания *операторов using*, которые помогают обеспечить правильную обработку объектов <xref:System.IDisposable>, таких как файлы и шрифты.</span><span class="sxs-lookup"><span data-stu-id="00129-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="00129-110">Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="00129-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="00129-111">Использование статического типа</span><span class="sxs-lookup"><span data-stu-id="00129-111">Using Static Type</span></span>  
 <span data-ttu-id="00129-112">Вы можете обращаться к статическим членам типа без необходимости квалификации доступа с помощью имени типа:</span><span class="sxs-lookup"><span data-stu-id="00129-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="00129-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="00129-113">Remarks</span></span>  
 <span data-ttu-id="00129-114">Область директивы `using` ограничена файлом, в котором она находится.</span><span class="sxs-lookup"><span data-stu-id="00129-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>
 
 <span data-ttu-id="00129-115">Директива `using` может отображаться:</span><span class="sxs-lookup"><span data-stu-id="00129-115">The `using` directive can appear:</span></span>
- <span data-ttu-id="00129-116">В начале файла исходного кода перед определением пространств имен и типов.</span><span class="sxs-lookup"><span data-stu-id="00129-116">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="00129-117">В пространстве имен перед любыми пространствами имен и типами, объявленными в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="00129-117">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="00129-118">В противном случае возникнет ошибка компилятора [CS1529](../../misc/cs1529.md).</span><span class="sxs-lookup"><span data-stu-id="00129-118">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>
  
 <span data-ttu-id="00129-119">Создайте директиву псевдонима `using`, чтобы упростить квалификацию идентификатора для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="00129-119">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="00129-120">Во всех директивах `using` следует использовать полное пространство имен или тип независимо от того, какие директивы `using` находятся перед ней.</span><span class="sxs-lookup"><span data-stu-id="00129-120">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="00129-121">В объявлении директивы `using` не может использоваться псевдоним `using`.</span><span class="sxs-lookup"><span data-stu-id="00129-121">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="00129-122">Например, следующий код вызовет ошибку компиляции:</span><span class="sxs-lookup"><span data-stu-id="00129-122">For example, the following generates a compiler error:</span></span>
 ```csharp
 using s = System.Text;
 using s.RegularExpressions; 
 ```
  
 <span data-ttu-id="00129-123">Создайте директиву `using`, чтобы использовать типы в пространстве имен без необходимости указания этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00129-123">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="00129-124">Директива `using` не предоставляет доступ к пространствам имен, вложенным в указанное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="00129-124">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="00129-125">Пространства имен делятся на две категории: пользовательские и системные.</span><span class="sxs-lookup"><span data-stu-id="00129-125">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="00129-126">Пользовательские пространства имен задаются в вашем коде.</span><span class="sxs-lookup"><span data-stu-id="00129-126">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="00129-127">Список системных пространств имен см. в разделе [Браузер API .NET](https://docs.microsoft.com/en-us/dotnet/api/).</span><span class="sxs-lookup"><span data-stu-id="00129-127">For a list of the system-defined namespaces, see [.NET API Browser](https://docs.microsoft.com/en-us/dotnet/api/).</span></span>  
  
 <span data-ttu-id="00129-128">Примеры ссылочных методов в других сборках см. в разделе [Создание и использование сборок в командной строке](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="00129-128">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="00129-129">Пример 1</span><span class="sxs-lookup"><span data-stu-id="00129-129">Example 1</span></span>  
  
 <span data-ttu-id="00129-130">В следующем примере показано, как задать и использовать псевдоним `using` для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00129-130">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="00129-131">Псевдоним using не может иметь открытый универсальный тип с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="00129-131">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="00129-132">Например, нельзя создать псевдоним using для List\<T>, но можно создать его для List\<int>.</span><span class="sxs-lookup"><span data-stu-id="00129-132">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="00129-133">Пример 2</span><span class="sxs-lookup"><span data-stu-id="00129-133">Example 2</span></span>  
  
 <span data-ttu-id="00129-134">В следующем примере показано, как задать директиву `using` и псевдоним `using` для класса.</span><span class="sxs-lookup"><span data-stu-id="00129-134">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="00129-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="00129-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00129-136">См. также</span><span class="sxs-lookup"><span data-stu-id="00129-136">See Also</span></span>

- [<span data-ttu-id="00129-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="00129-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="00129-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="00129-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="00129-139">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="00129-139">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
- [<span data-ttu-id="00129-140">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="00129-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="00129-141">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="00129-141">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="00129-142">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="00129-142">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="00129-143">Оператор using</span><span class="sxs-lookup"><span data-stu-id="00129-143">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
