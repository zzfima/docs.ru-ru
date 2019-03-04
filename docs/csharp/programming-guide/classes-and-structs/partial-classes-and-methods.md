---
title: Руководство по программированию на C#. Разделяемые классы и методы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 7e91d77393c4d2980cce73a92589b752124e8077
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965206"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="1b792-102">Разделяемые классы и методы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="1b792-102">Partial Classes and Methods (C# Programming Guide)</span></span>
<span data-ttu-id="1b792-103">Можно разделить определение [класса](../../../csharp/language-reference/keywords/class.md), [структуры](../../../csharp/language-reference/keywords/struct.md), [интерфейса](../../../csharp/language-reference/keywords/interface.md) или метода между двумя или более исходными файлами.</span><span class="sxs-lookup"><span data-stu-id="1b792-103">It is possible to split the definition of a [class](../../../csharp/language-reference/keywords/class.md), a [struct](../../../csharp/language-reference/keywords/struct.md), an [interface](../../../csharp/language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="1b792-104">Каждый исходный файл содержит часть определения класса или метода, а во время компиляции приложения все части объединяются.</span><span class="sxs-lookup"><span data-stu-id="1b792-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>  
  
## <a name="partial-classes"></a><span data-ttu-id="1b792-105">Разделяемые классы</span><span class="sxs-lookup"><span data-stu-id="1b792-105">Partial Classes</span></span>  
 <span data-ttu-id="1b792-106">Существует несколько ситуаций, когда желательно разделение определения класса.</span><span class="sxs-lookup"><span data-stu-id="1b792-106">There are several situations when splitting a class definition is desirable:</span></span>  
  
-   <span data-ttu-id="1b792-107">При работе над большими проектами распределение класса между различными файлами позволяет нескольким программистам работать с ним одновременно.</span><span class="sxs-lookup"><span data-stu-id="1b792-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>  
  
-   <span data-ttu-id="1b792-108">При работе с использованием автоматически создаваемого источника код можно добавлять в класс без повторного создания файла источника.</span><span class="sxs-lookup"><span data-stu-id="1b792-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="1b792-109">Visual Studio использует этот подход при создании форм Windows Forms, кода оболочки веб-службы и т. д.</span><span class="sxs-lookup"><span data-stu-id="1b792-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="1b792-110">Можно создать код, который использует эти классы, без необходимости изменения файла, созданного в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1b792-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>  
  
-   <span data-ttu-id="1b792-111">Чтобы разделить определение класса, используйте модификатор ключевого слова [partial](../../../csharp/language-reference/keywords/partial-type.md), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="1b792-111">To split a class definition, use the [partial](../../../csharp/language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]  
  
 <span data-ttu-id="1b792-112">Ключевое слово `partial` указывает, что другие части класса, структуры или интерфейса могут быть определены в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="1b792-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="1b792-113">Все части должны использовать ключевое слово `partial`.</span><span class="sxs-lookup"><span data-stu-id="1b792-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="1b792-114">Для формирования окончательного типа все части должны быть доступны во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1b792-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="1b792-115">Все части должны иметь одинаковые модификаторы доступа, например `public`, `private` и т. д.</span><span class="sxs-lookup"><span data-stu-id="1b792-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>  
  
 <span data-ttu-id="1b792-116">Если какая-либо из частей объявлена абстрактной, то весь тип будет считаться абстрактным.</span><span class="sxs-lookup"><span data-stu-id="1b792-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="1b792-117">Если какая-либо из частей объявлена запечатанной, то весь тип будет считаться запечатанным.</span><span class="sxs-lookup"><span data-stu-id="1b792-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="1b792-118">Если какая-либо из частей объявляет базовый тип, то весь тип будет наследовать данный класс.</span><span class="sxs-lookup"><span data-stu-id="1b792-118">If any part declares a base type, then the whole type inherits that class.</span></span>  
  
 <span data-ttu-id="1b792-119">Все части, указывающие базовый класс, должны быть согласованы друг с другом, а части, не использующие базовый класс, все равно наследуют базовый тип.</span><span class="sxs-lookup"><span data-stu-id="1b792-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="1b792-120">Части могут указывать различные базовые интерфейсы, и окончательный тип будет реализовывать все интерфейсы, перечисленные во всех разделяемых объявлениях.</span><span class="sxs-lookup"><span data-stu-id="1b792-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="1b792-121">Любые члены класса, структуры или интерфейса, объявленные в разделяемом объявлении, доступны для всех остальных частей.</span><span class="sxs-lookup"><span data-stu-id="1b792-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="1b792-122">Окончательный тип представляет собой комбинацию всех частей, выполненную во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1b792-122">The final type is the combination of all the parts at compile time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b792-123">Модификатор `partial` недоступен в объявлениях делегатов или перечислений.</span><span class="sxs-lookup"><span data-stu-id="1b792-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>  
  
 <span data-ttu-id="1b792-124">В следующем примере показано, что вложенные типы могут быть разделяемыми, даже если тип, в который они вложены, не является разделяемым.</span><span class="sxs-lookup"><span data-stu-id="1b792-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>  
  
 [!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]  
  
 <span data-ttu-id="1b792-125">Во время компиляции атрибуты определений разделяемого типа объединяются.</span><span class="sxs-lookup"><span data-stu-id="1b792-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="1b792-126">В качестве примера рассмотрим следующие объявления:</span><span class="sxs-lookup"><span data-stu-id="1b792-126">For example, consider the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]  
  
 <span data-ttu-id="1b792-127">Они эквивалентны следующим объявлениям:</span><span class="sxs-lookup"><span data-stu-id="1b792-127">They are equivalent to the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]  
  
 <span data-ttu-id="1b792-128">Следующие элементы объединяются из всех определений разделяемого типа:</span><span class="sxs-lookup"><span data-stu-id="1b792-128">The following are merged from all the partial-type definitions:</span></span>  
  
-   <span data-ttu-id="1b792-129">XML-комментарии</span><span class="sxs-lookup"><span data-stu-id="1b792-129">XML comments</span></span>  
  
-   <span data-ttu-id="1b792-130">интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1b792-130">interfaces</span></span>  
  
-   <span data-ttu-id="1b792-131">атрибуты параметров универсального параметра</span><span class="sxs-lookup"><span data-stu-id="1b792-131">generic-type parameter attributes</span></span>  
  
-   <span data-ttu-id="1b792-132">атрибуты классов</span><span class="sxs-lookup"><span data-stu-id="1b792-132">class attributes</span></span>  
  
-   <span data-ttu-id="1b792-133">члены</span><span class="sxs-lookup"><span data-stu-id="1b792-133">members</span></span>  
  
 <span data-ttu-id="1b792-134">В качестве примера рассмотрим следующие объявления:</span><span class="sxs-lookup"><span data-stu-id="1b792-134">For example, consider the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]  
  
 <span data-ttu-id="1b792-135">Они эквивалентны следующим объявлениям:</span><span class="sxs-lookup"><span data-stu-id="1b792-135">They are equivalent to the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]  
  
### <a name="restrictions"></a><span data-ttu-id="1b792-136">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1b792-136">Restrictions</span></span>  
 <span data-ttu-id="1b792-137">Имеется несколько правил, которые необходимо выполнять при работе с определениями разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="1b792-137">There are several rules to follow when you are working with partial class definitions:</span></span>  
  
-   <span data-ttu-id="1b792-138">Все определения разделяемого типа, являющиеся частями одного типа, должны изменяться с использованием типа `partial`.</span><span class="sxs-lookup"><span data-stu-id="1b792-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="1b792-139">Например, следующие объявления класса приведут к появлению ошибки:</span><span class="sxs-lookup"><span data-stu-id="1b792-139">For example, the following class declarations generate an error:</span></span>  
  
     [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]  
  
-   <span data-ttu-id="1b792-140">Модификатор `partial` должен находиться непосредственно перед ключевыми словами `class`, `struct` или `interface`.</span><span class="sxs-lookup"><span data-stu-id="1b792-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>  
  
-   <span data-ttu-id="1b792-141">В определениях разделяемого типа могут присутствовать вложенные разделяемые типы, что показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1b792-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>  
  
     [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]  
  
-   <span data-ttu-id="1b792-142">Все определения разделяемого типа, являющиеся частями одного и того же типа, должны быть определены в одной сборке и в одном модуле (EXE-файл или DLL-файл).</span><span class="sxs-lookup"><span data-stu-id="1b792-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="1b792-143">Разделяемые определения не могут находиться в разных модулях.</span><span class="sxs-lookup"><span data-stu-id="1b792-143">Partial definitions cannot span multiple modules.</span></span>  
  
-   <span data-ttu-id="1b792-144">Имя класса и параметры универсального типа должны соответствовать всем определениям разделяемого типа.</span><span class="sxs-lookup"><span data-stu-id="1b792-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="1b792-145">Универсальные типы могут быть разделяемыми.</span><span class="sxs-lookup"><span data-stu-id="1b792-145">Generic types can be partial.</span></span> <span data-ttu-id="1b792-146">Все объявления разделяемого типа должны использовать одинаковые имена параметров в одном и том же порядке.</span><span class="sxs-lookup"><span data-stu-id="1b792-146">Each partial declaration must use the same parameter names in the same order.</span></span>  
  
-   <span data-ttu-id="1b792-147">Приведенные ниже ключевые слова необязательно должны присутствовать в определении разделяемого типа, но если они присутствуют в одном определении разделяемого типа, то не должны конфликтовать с ключевыми словами, указанными в других определениях того же разделяемого типа.</span><span class="sxs-lookup"><span data-stu-id="1b792-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>  
  
    -   [<span data-ttu-id="1b792-148">public</span><span class="sxs-lookup"><span data-stu-id="1b792-148">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
    -   [<span data-ttu-id="1b792-149">private</span><span class="sxs-lookup"><span data-stu-id="1b792-149">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
    -   [<span data-ttu-id="1b792-150">protected</span><span class="sxs-lookup"><span data-stu-id="1b792-150">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [<span data-ttu-id="1b792-151">internal</span><span class="sxs-lookup"><span data-stu-id="1b792-151">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [<span data-ttu-id="1b792-152">abstract</span><span class="sxs-lookup"><span data-stu-id="1b792-152">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [<span data-ttu-id="1b792-153">sealed</span><span class="sxs-lookup"><span data-stu-id="1b792-153">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   <span data-ttu-id="1b792-154">базовый класс</span><span class="sxs-lookup"><span data-stu-id="1b792-154">base class</span></span>  
  
    -   <span data-ttu-id="1b792-155">модификатор [new](../../../csharp/language-reference/keywords/new.md) (вложенные части)</span><span class="sxs-lookup"><span data-stu-id="1b792-155">[new](../../../csharp/language-reference/keywords/new.md) modifier (nested parts)</span></span>  
  
    -   <span data-ttu-id="1b792-156">универсальные ограничения</span><span class="sxs-lookup"><span data-stu-id="1b792-156">generic constraints</span></span>  
  
         <span data-ttu-id="1b792-157">Дополнительные сведения см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1b792-157">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="1b792-158">Пример 1</span><span class="sxs-lookup"><span data-stu-id="1b792-158">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="1b792-159">Описание</span><span class="sxs-lookup"><span data-stu-id="1b792-159">Description</span></span>  
 <span data-ttu-id="1b792-160">В следующем примере поля и конструктор класса `Coords` объявлены в одном определении разделяемого класса, а член `PrintCoords` — в другом определении разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="1b792-160">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1b792-161">Код</span><span class="sxs-lookup"><span data-stu-id="1b792-161">Code</span></span>  
 [!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]  
  
## <a name="example-2"></a><span data-ttu-id="1b792-162">Пример 2</span><span class="sxs-lookup"><span data-stu-id="1b792-162">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="1b792-163">Описание</span><span class="sxs-lookup"><span data-stu-id="1b792-163">Description</span></span>  
 <span data-ttu-id="1b792-164">В следующем примере показано, что можно также разработать разделяемые структуры и интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1b792-164">The following example shows that you can also develop partial structs and interfaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1b792-165">Код</span><span class="sxs-lookup"><span data-stu-id="1b792-165">Code</span></span>  
 [!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]  
  
## <a name="partial-methods"></a><span data-ttu-id="1b792-166">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="1b792-166">Partial Methods</span></span>  
 <span data-ttu-id="1b792-167">Разделяемый класс или структура могут содержать разделяемый метод.</span><span class="sxs-lookup"><span data-stu-id="1b792-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="1b792-168">Одна часть класса содержит сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="1b792-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="1b792-169">В той же или в другой части можно определить дополнительную реализацию.</span><span class="sxs-lookup"><span data-stu-id="1b792-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="1b792-170">Если реализация не предоставлена, метод и все вызовы метода удаляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1b792-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>  
  
 <span data-ttu-id="1b792-171">Разделяемые методы позволяют разработчику одной части класса определить метод, схожий с событием.</span><span class="sxs-lookup"><span data-stu-id="1b792-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="1b792-172">Разработчик другой части класса может решить, реализовывать этот метод или нет.</span><span class="sxs-lookup"><span data-stu-id="1b792-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="1b792-173">Если метод не реализован, то компилятор удаляет сигнатуру метода и все вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="1b792-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="1b792-174">Вызовы метода, включая любые результаты, которые могли бы произойти от оценки аргументов в вызовах, не имеют эффекта во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b792-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="1b792-175">Таким образом, любой код в разделяемом классе может свободно использовать разделяемый метод, даже если реализация не предоставлена.</span><span class="sxs-lookup"><span data-stu-id="1b792-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="1b792-176">Во время компиляции и выполнения программы не возникнут никакие ошибки, если метод будет вызван, но не реализован.</span><span class="sxs-lookup"><span data-stu-id="1b792-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>  
  
 <span data-ttu-id="1b792-177">Разделяемые методы особенно полезны для настройки автоматически созданного кода.</span><span class="sxs-lookup"><span data-stu-id="1b792-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="1b792-178">Они позволяют зарезервировать имя и сигнатуру метода, чтобы автоматически созданный код мог вызвать метод, а разработчик мог сам решить, реализовывать этот метод или нет.</span><span class="sxs-lookup"><span data-stu-id="1b792-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="1b792-179">Как и разделяемые классы, разделяемые методы позволяют организовать совместную работу автоматически созданного кода и кода, созданного человеком, без дополнительных затрат во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b792-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>  
  
 <span data-ttu-id="1b792-180">Объявление разделяемого метода состоит из двух частей: определения и реализации.</span><span class="sxs-lookup"><span data-stu-id="1b792-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="1b792-181">Они могут находиться в разных частях или в одной и той же части разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="1b792-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="1b792-182">Если объявление реализации отсутствует, то компилятор оптимизирует код, удаляя как объявление определения, так и все вызовы метода.</span><span class="sxs-lookup"><span data-stu-id="1b792-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>  
  
```csharp  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   <span data-ttu-id="1b792-183">Объявления разделяемого метода должны начинаться с контекстно-зависимого ключевого слова [partial](../../../csharp/language-reference/keywords/partial-type.md), а метод должен возвращать значение типа [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="1b792-183">Partial method declarations must begin with the contextual keyword [partial](../../../csharp/language-reference/keywords/partial-type.md) and the method must return [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
-   <span data-ttu-id="1b792-184">Разделяемые методы могут иметь параметры [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) или [ref](../../../csharp/language-reference/keywords/ref.md), но не [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="1b792-184">Partial methods can have [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) but not [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>  
  
-   <span data-ttu-id="1b792-185">Разделяемые методы неявно имеют модификатор [private](../../../csharp/language-reference/keywords/private.md) и поэтому не могут иметь модификатор [virtual](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="1b792-185">Partial methods are implicitly [private](../../../csharp/language-reference/keywords/private.md), and therefore they cannot be [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
-   <span data-ttu-id="1b792-186">Разделяемые методы не могут иметь модификатор [extern](../../../csharp/language-reference/keywords/extern.md), поскольку наличие тела определяет, выполняется ли их определение или реализация.</span><span class="sxs-lookup"><span data-stu-id="1b792-186">Partial methods cannot be [extern](../../../csharp/language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>  
  
-   <span data-ttu-id="1b792-187">Разделяемые методы могут иметь модификаторы [static](../../../csharp/language-reference/keywords/static.md) и [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="1b792-187">Partial methods can have [static](../../../csharp/language-reference/keywords/static.md) and [unsafe](../../../csharp/language-reference/keywords/unsafe.md) modifiers.</span></span>  
  
-   <span data-ttu-id="1b792-188">Разделяемые методы могут быть универсальными.</span><span class="sxs-lookup"><span data-stu-id="1b792-188">Partial methods can be generic.</span></span> <span data-ttu-id="1b792-189">Ограничения налагаются на ту часть объявления разделяемого метода, где находится определение, и могут дополнительно повторяться в разделе реализации.</span><span class="sxs-lookup"><span data-stu-id="1b792-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="1b792-190">Имена параметров и типов параметров необязательно должны совпадать в объявлении реализации и в объявлении определения.</span><span class="sxs-lookup"><span data-stu-id="1b792-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>  
  
-   <span data-ttu-id="1b792-191">Можно использовать [делегат](../../../csharp/language-reference/keywords/delegate.md) в качестве определенного и реализованного разделяемого метода, но его нельзя использовать в качестве разделяемого метода, который только определен.</span><span class="sxs-lookup"><span data-stu-id="1b792-191">You can make a [delegate](../../../csharp/language-reference/keywords/delegate.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1b792-192">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1b792-192">C# Language Specification</span></span>  

<span data-ttu-id="1b792-193">Дополнительные сведения см. в разделе [Разделяемые типы](~/_csharplang/spec/classes.md#partial-types) в [Спецификации языка C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1b792-193">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="1b792-194">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="1b792-194">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b792-195">См. также</span><span class="sxs-lookup"><span data-stu-id="1b792-195">See also</span></span>

- [<span data-ttu-id="1b792-196">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1b792-196">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1b792-197">Классы</span><span class="sxs-lookup"><span data-stu-id="1b792-197">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
- [<span data-ttu-id="1b792-198">Структуры</span><span class="sxs-lookup"><span data-stu-id="1b792-198">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="1b792-199">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1b792-199">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="1b792-200">partial (тип)</span><span class="sxs-lookup"><span data-stu-id="1b792-200">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
