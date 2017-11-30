---
title: "Директива using (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 02c50b1e7a54d776985b60570c898e7d0739c44c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="190b0-102">Директива using (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="190b0-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="190b0-103">Директива `using` используется в следующих трех целях.</span><span class="sxs-lookup"><span data-stu-id="190b0-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="190b0-104">Для разрешения использования типов в пространстве имен, чтобы не нужно было квалифицировать использование типа в этом пространстве имен:</span><span class="sxs-lookup"><span data-stu-id="190b0-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="190b0-105">Для разрешения доступа к статическим членам типа без необходимости квалификации доступа с помощью имени типа:</span><span class="sxs-lookup"><span data-stu-id="190b0-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="190b0-106">Дополнительные сведения см. в разделе [Директива using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="190b0-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="190b0-107">Чтобы создать псевдоним для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="190b0-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="190b0-108">Это называется *директивой using static*.</span><span class="sxs-lookup"><span data-stu-id="190b0-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="190b0-109">Ключевое слово `using` также используется для создания *операторов using*, которые помогают обеспечить правильную обработку объектов <xref:System.IDisposable>, таких как файлы и шрифты.</span><span class="sxs-lookup"><span data-stu-id="190b0-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="190b0-110">Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="190b0-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="190b0-111">Использование статического типа</span><span class="sxs-lookup"><span data-stu-id="190b0-111">Using Static Type</span></span>  
 <span data-ttu-id="190b0-112">Вы можете обращаться к статическим членам типа без необходимости квалификации доступа с помощью имени типа:</span><span class="sxs-lookup"><span data-stu-id="190b0-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="190b0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="190b0-113">Remarks</span></span>  
 <span data-ttu-id="190b0-114">Область директивы `using` ограничена файлом, в котором она находится.</span><span class="sxs-lookup"><span data-stu-id="190b0-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="190b0-115">Создайте псевдоним `using`, чтобы упростить квалификацию идентификатора для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="190b0-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="190b0-116">Правая часть директивы псевдонима using всегда должна быть полным типом независимо от директив using до нее.</span><span class="sxs-lookup"><span data-stu-id="190b0-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="190b0-117">Создайте директиву `using`, чтобы использовать типы в пространстве имен без необходимости указания этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="190b0-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="190b0-118">Директива `using` не предоставляет доступ к пространствам имен, вложенным в указанное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="190b0-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="190b0-119">Пространства имен делятся на две категории: пользовательские и системные.</span><span class="sxs-lookup"><span data-stu-id="190b0-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="190b0-120">Пользовательские пространства имен задаются в вашем коде.</span><span class="sxs-lookup"><span data-stu-id="190b0-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="190b0-121">Список системных пространств имен см. в разделе [Общие сведения о библиотеке классов .NET Framework](../../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="190b0-121">For a list of the system-defined namespaces, see [.NET Framework Class Library Overview](../../../standard/class-library-overview.md).</span></span>  
  
 <span data-ttu-id="190b0-122">Примеры ссылочных методов в других сборках см. в разделе [Создание и использование сборок с помощью командной строки](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="190b0-122">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="190b0-123">Пример 1</span><span class="sxs-lookup"><span data-stu-id="190b0-123">Example 1</span></span>  
  
 <span data-ttu-id="190b0-124">В следующем примере показано, как задать и использовать псевдоним `using` для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="190b0-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="190b0-125">Псевдоним using не может иметь открытый универсальный тип с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="190b0-125">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="190b0-126">Например, нельзя создать псевдоним using для List\<T>, но можно создать его для List\<int>.</span><span class="sxs-lookup"><span data-stu-id="190b0-126">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="190b0-127">Пример 2</span><span class="sxs-lookup"><span data-stu-id="190b0-127">Example 2</span></span>  
  
 <span data-ttu-id="190b0-128">В следующем примере показано, как задать директиву `using` и псевдоним `using` для класса.</span><span class="sxs-lookup"><span data-stu-id="190b0-128">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="190b0-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="190b0-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="190b0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="190b0-130">See Also</span></span>  
 [<span data-ttu-id="190b0-131">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="190b0-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="190b0-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="190b0-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="190b0-133">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="190b0-133">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
 [<span data-ttu-id="190b0-134">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="190b0-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="190b0-135">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="190b0-135">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="190b0-136">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="190b0-136">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="190b0-137">Оператор using</span><span class="sxs-lookup"><span data-stu-id="190b0-137">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
