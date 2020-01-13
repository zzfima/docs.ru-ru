---
title: Руководство по программированию на C#. Разделяемые классы и методы
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: ea8d95c41df236897761ace1062ec325a069d52b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714747"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="15eba-102">Разделяемые классы и методы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="15eba-102">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="15eba-103">Можно разделить определение [класса](../../language-reference/keywords/class.md), [структуры](../../language-reference/keywords/struct.md), [интерфейса](../../language-reference/keywords/interface.md) или метода между двумя или более исходными файлами.</span><span class="sxs-lookup"><span data-stu-id="15eba-103">It is possible to split the definition of a [class](../../language-reference/keywords/class.md), a [struct](../../language-reference/keywords/struct.md), an [interface](../../language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="15eba-104">Каждый исходный файл содержит часть определения класса или метода, а во время компиляции приложения все части объединяются.</span><span class="sxs-lookup"><span data-stu-id="15eba-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="15eba-105">Разделяемые классы</span><span class="sxs-lookup"><span data-stu-id="15eba-105">Partial Classes</span></span>

<span data-ttu-id="15eba-106">Существует несколько ситуаций, когда желательно разделение определения класса.</span><span class="sxs-lookup"><span data-stu-id="15eba-106">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="15eba-107">При работе над большими проектами распределение класса между различными файлами позволяет нескольким программистам работать с ним одновременно.</span><span class="sxs-lookup"><span data-stu-id="15eba-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="15eba-108">При работе с использованием автоматически создаваемого источника код можно добавлять в класс без повторного создания файла источника.</span><span class="sxs-lookup"><span data-stu-id="15eba-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="15eba-109">Visual Studio использует этот подход при создании форм Windows Forms, кода оболочки веб-службы и т. д.</span><span class="sxs-lookup"><span data-stu-id="15eba-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="15eba-110">Можно создать код, который использует эти классы, без необходимости изменения файла, созданного в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="15eba-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="15eba-111">Чтобы разделить определение класса, используйте модификатор ключевого слова [partial](../../language-reference/keywords/partial-type.md), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="15eba-111">To split a class definition, use the [partial](../../language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

<span data-ttu-id="15eba-112">Ключевое слово `partial` указывает, что другие части класса, структуры или интерфейса могут быть определены в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="15eba-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="15eba-113">Все части должны использовать ключевое слово `partial`.</span><span class="sxs-lookup"><span data-stu-id="15eba-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="15eba-114">Для формирования окончательного типа все части должны быть доступны во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="15eba-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="15eba-115">Все части должны иметь одинаковые модификаторы доступа, например `public`, `private` и т. д.</span><span class="sxs-lookup"><span data-stu-id="15eba-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="15eba-116">Если какая-либо из частей объявлена абстрактной, то весь тип будет считаться абстрактным.</span><span class="sxs-lookup"><span data-stu-id="15eba-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="15eba-117">Если какая-либо из частей объявлена запечатанной, то весь тип будет считаться запечатанным.</span><span class="sxs-lookup"><span data-stu-id="15eba-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="15eba-118">Если какая-либо из частей объявляет базовый тип, то весь тип будет наследовать данный класс.</span><span class="sxs-lookup"><span data-stu-id="15eba-118">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="15eba-119">Все части, указывающие базовый класс, должны быть согласованы друг с другом, а части, не использующие базовый класс, все равно наследуют базовый тип.</span><span class="sxs-lookup"><span data-stu-id="15eba-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="15eba-120">Части могут указывать различные базовые интерфейсы, и окончательный тип будет реализовывать все интерфейсы, перечисленные во всех разделяемых объявлениях.</span><span class="sxs-lookup"><span data-stu-id="15eba-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="15eba-121">Любые члены класса, структуры или интерфейса, объявленные в разделяемом объявлении, доступны для всех остальных частей.</span><span class="sxs-lookup"><span data-stu-id="15eba-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="15eba-122">Окончательный тип представляет собой комбинацию всех частей, выполненную во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="15eba-122">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="15eba-123">Модификатор `partial` недоступен в объявлениях делегатов или перечислений.</span><span class="sxs-lookup"><span data-stu-id="15eba-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="15eba-124">В следующем примере показано, что вложенные типы могут быть разделяемыми, даже если тип, в который они вложены, не является разделяемым.</span><span class="sxs-lookup"><span data-stu-id="15eba-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

<span data-ttu-id="15eba-125">Во время компиляции атрибуты определений разделяемого типа объединяются.</span><span class="sxs-lookup"><span data-stu-id="15eba-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="15eba-126">В качестве примера рассмотрим следующие объявления:</span><span class="sxs-lookup"><span data-stu-id="15eba-126">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

<span data-ttu-id="15eba-127">Они эквивалентны следующим объявлениям:</span><span class="sxs-lookup"><span data-stu-id="15eba-127">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

<span data-ttu-id="15eba-128">Следующие элементы объединяются из всех определений разделяемого типа:</span><span class="sxs-lookup"><span data-stu-id="15eba-128">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="15eba-129">XML-комментарии</span><span class="sxs-lookup"><span data-stu-id="15eba-129">XML comments</span></span>

- <span data-ttu-id="15eba-130">интерфейсы</span><span class="sxs-lookup"><span data-stu-id="15eba-130">interfaces</span></span>

- <span data-ttu-id="15eba-131">атрибуты параметров универсального параметра</span><span class="sxs-lookup"><span data-stu-id="15eba-131">generic-type parameter attributes</span></span>

- <span data-ttu-id="15eba-132">атрибуты классов</span><span class="sxs-lookup"><span data-stu-id="15eba-132">class attributes</span></span>

- <span data-ttu-id="15eba-133">члены</span><span class="sxs-lookup"><span data-stu-id="15eba-133">members</span></span>

<span data-ttu-id="15eba-134">В качестве примера рассмотрим следующие объявления:</span><span class="sxs-lookup"><span data-stu-id="15eba-134">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

<span data-ttu-id="15eba-135">Они эквивалентны следующим объявлениям:</span><span class="sxs-lookup"><span data-stu-id="15eba-135">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a><span data-ttu-id="15eba-136">Ограничения</span><span class="sxs-lookup"><span data-stu-id="15eba-136">Restrictions</span></span>

<span data-ttu-id="15eba-137">Имеется несколько правил, которые необходимо выполнять при работе с определениями разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="15eba-137">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="15eba-138">Все определения разделяемого типа, являющиеся частями одного типа, должны изменяться с использованием типа `partial`.</span><span class="sxs-lookup"><span data-stu-id="15eba-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="15eba-139">Например, следующие объявления класса приведут к появлению ошибки:</span><span class="sxs-lookup"><span data-stu-id="15eba-139">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- <span data-ttu-id="15eba-140">Модификатор `partial` должен находиться непосредственно перед ключевыми словами `class`, `struct` или `interface`.</span><span class="sxs-lookup"><span data-stu-id="15eba-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="15eba-141">В определениях разделяемого типа могут присутствовать вложенные разделяемые типы, что показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="15eba-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- <span data-ttu-id="15eba-142">Все определения разделяемого типа, являющиеся частями одного и того же типа, должны быть определены в одной сборке и в одном модуле (EXE-файл или DLL-файл).</span><span class="sxs-lookup"><span data-stu-id="15eba-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="15eba-143">Разделяемые определения не могут находиться в разных модулях.</span><span class="sxs-lookup"><span data-stu-id="15eba-143">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="15eba-144">Имя класса и параметры универсального типа должны соответствовать всем определениям разделяемого типа.</span><span class="sxs-lookup"><span data-stu-id="15eba-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="15eba-145">Универсальные типы могут быть разделяемыми.</span><span class="sxs-lookup"><span data-stu-id="15eba-145">Generic types can be partial.</span></span> <span data-ttu-id="15eba-146">Все объявления разделяемого типа должны использовать одинаковые имена параметров в одном и том же порядке.</span><span class="sxs-lookup"><span data-stu-id="15eba-146">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="15eba-147">Приведенные ниже ключевые слова необязательно должны присутствовать в определении разделяемого типа, но если они присутствуют в одном определении разделяемого типа, то не должны конфликтовать с ключевыми словами, указанными в других определениях того же разделяемого типа.</span><span class="sxs-lookup"><span data-stu-id="15eba-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="15eba-148">public</span><span class="sxs-lookup"><span data-stu-id="15eba-148">public</span></span>](../../language-reference/keywords/public.md)

  - [<span data-ttu-id="15eba-149">private</span><span class="sxs-lookup"><span data-stu-id="15eba-149">private</span></span>](../../language-reference/keywords/private.md)

  - [<span data-ttu-id="15eba-150">protected</span><span class="sxs-lookup"><span data-stu-id="15eba-150">protected</span></span>](../../language-reference/keywords/protected.md)

  - [<span data-ttu-id="15eba-151">internal</span><span class="sxs-lookup"><span data-stu-id="15eba-151">internal</span></span>](../../language-reference/keywords/internal.md)

  - [<span data-ttu-id="15eba-152">abstract</span><span class="sxs-lookup"><span data-stu-id="15eba-152">abstract</span></span>](../../language-reference/keywords/abstract.md)

  - [<span data-ttu-id="15eba-153">sealed</span><span class="sxs-lookup"><span data-stu-id="15eba-153">sealed</span></span>](../../language-reference/keywords/sealed.md)

  - <span data-ttu-id="15eba-154">базовый класс</span><span class="sxs-lookup"><span data-stu-id="15eba-154">base class</span></span>

  - <span data-ttu-id="15eba-155">модификатор [new](../../language-reference/keywords/new-modifier.md) (вложенные части)</span><span class="sxs-lookup"><span data-stu-id="15eba-155">[new](../../language-reference/keywords/new-modifier.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="15eba-156">универсальные ограничения</span><span class="sxs-lookup"><span data-stu-id="15eba-156">generic constraints</span></span>

<span data-ttu-id="15eba-157">Дополнительные сведения см. в разделе [Ограничения параметров типа](../generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="15eba-157">For more information, see [Constraints on Type Parameters](../generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="15eba-158">Пример 1</span><span class="sxs-lookup"><span data-stu-id="15eba-158">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="15eba-159">Описание</span><span class="sxs-lookup"><span data-stu-id="15eba-159">Description</span></span>

<span data-ttu-id="15eba-160">В следующем примере поля и конструктор класса `Coords` объявлены в одном определении разделяемого класса, а член `PrintCoords` — в другом определении разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="15eba-160">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="15eba-161">Код</span><span class="sxs-lookup"><span data-stu-id="15eba-161">Code</span></span>

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a><span data-ttu-id="15eba-162">Пример 2</span><span class="sxs-lookup"><span data-stu-id="15eba-162">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="15eba-163">Описание</span><span class="sxs-lookup"><span data-stu-id="15eba-163">Description</span></span>

<span data-ttu-id="15eba-164">В следующем примере показано, что можно также разработать разделяемые структуры и интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="15eba-164">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="15eba-165">Код</span><span class="sxs-lookup"><span data-stu-id="15eba-165">Code</span></span>

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a><span data-ttu-id="15eba-166">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="15eba-166">Partial Methods</span></span>

<span data-ttu-id="15eba-167">Разделяемый класс или структура могут содержать разделяемый метод.</span><span class="sxs-lookup"><span data-stu-id="15eba-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="15eba-168">Одна часть класса содержит сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="15eba-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="15eba-169">В той же или в другой части можно определить дополнительную реализацию.</span><span class="sxs-lookup"><span data-stu-id="15eba-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="15eba-170">Если реализация не предоставлена, метод и все вызовы метода удаляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="15eba-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="15eba-171">Разделяемые методы позволяют разработчику одной части класса определить метод, схожий с событием.</span><span class="sxs-lookup"><span data-stu-id="15eba-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="15eba-172">Разработчик другой части класса может решить, реализовывать этот метод или нет.</span><span class="sxs-lookup"><span data-stu-id="15eba-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="15eba-173">Если метод не реализован, то компилятор удаляет сигнатуру метода и все вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="15eba-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="15eba-174">Вызовы метода, включая любые результаты, которые могли бы произойти от оценки аргументов в вызовах, не имеют эффекта во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15eba-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="15eba-175">Таким образом, любой код в разделяемом классе может свободно использовать разделяемый метод, даже если реализация не предоставлена.</span><span class="sxs-lookup"><span data-stu-id="15eba-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="15eba-176">Во время компиляции и выполнения программы не возникнут никакие ошибки, если метод будет вызван, но не реализован.</span><span class="sxs-lookup"><span data-stu-id="15eba-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="15eba-177">Разделяемые методы особенно полезны для настройки автоматически созданного кода.</span><span class="sxs-lookup"><span data-stu-id="15eba-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="15eba-178">Они позволяют зарезервировать имя и сигнатуру метода, чтобы автоматически созданный код мог вызвать метод, а разработчик мог сам решить, реализовывать этот метод или нет.</span><span class="sxs-lookup"><span data-stu-id="15eba-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="15eba-179">Как и разделяемые классы, разделяемые методы позволяют организовать совместную работу автоматически созданного кода и кода, созданного человеком, без дополнительных затрат во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15eba-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="15eba-180">Объявление разделяемого метода состоит из двух частей: определения и реализации.</span><span class="sxs-lookup"><span data-stu-id="15eba-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="15eba-181">Они могут находиться в разных частях или в одной и той же части разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="15eba-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="15eba-182">Если объявление реализации отсутствует, то компилятор оптимизирует код, удаляя как объявление определения, так и все вызовы метода.</span><span class="sxs-lookup"><span data-stu-id="15eba-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="15eba-183">Объявления разделяемого метода должны начинаться с контекстно-зависимого ключевого слова [partial](../../language-reference/keywords/partial-type.md), а метод должен возвращать значение типа [void](../../language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="15eba-183">Partial method declarations must begin with the contextual keyword [partial](../../language-reference/keywords/partial-type.md) and the method must return [void](../../language-reference/keywords/void.md).</span></span>

- <span data-ttu-id="15eba-184">Разделяемые методы могут иметь параметры [in](../../language-reference/keywords/in-parameter-modifier.md) или [ref](../../language-reference/keywords/ref.md), но не [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="15eba-184">Partial methods can have [in](../../language-reference/keywords/in-parameter-modifier.md) or [ref](../../language-reference/keywords/ref.md) but not [out](../../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="15eba-185">Разделяемые методы неявно имеют модификатор [private](../../language-reference/keywords/private.md) и поэтому не могут иметь модификатор [virtual](../../language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="15eba-185">Partial methods are implicitly [private](../../language-reference/keywords/private.md), and therefore they cannot be [virtual](../../language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="15eba-186">Разделяемые методы не могут иметь модификатор [extern](../../language-reference/keywords/extern.md), поскольку наличие тела определяет, выполняется ли их определение или реализация.</span><span class="sxs-lookup"><span data-stu-id="15eba-186">Partial methods cannot be [extern](../../language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="15eba-187">Разделяемые методы могут иметь модификаторы [static](../../language-reference/keywords/static.md) и [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="15eba-187">Partial methods can have [static](../../language-reference/keywords/static.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="15eba-188">Разделяемые методы могут быть универсальными.</span><span class="sxs-lookup"><span data-stu-id="15eba-188">Partial methods can be generic.</span></span> <span data-ttu-id="15eba-189">Ограничения налагаются на ту часть объявления разделяемого метода, где находится определение, и могут дополнительно повторяться в разделе реализации.</span><span class="sxs-lookup"><span data-stu-id="15eba-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="15eba-190">Имена параметров и типов параметров необязательно должны совпадать в объявлении реализации и в объявлении определения.</span><span class="sxs-lookup"><span data-stu-id="15eba-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="15eba-191">Можно использовать [делегат](../../language-reference/builtin-types/reference-types.md) в качестве определенного и реализованного разделяемого метода, но его нельзя использовать в качестве разделяемого метода, который только определен.</span><span class="sxs-lookup"><span data-stu-id="15eba-191">You can make a [delegate](../../language-reference/builtin-types/reference-types.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="15eba-192">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="15eba-192">C# Language Specification</span></span>

<span data-ttu-id="15eba-193">Дополнительные сведения см. в разделе [Разделяемые типы](~/_csharplang/spec/classes.md#partial-types) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="15eba-193">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="15eba-194">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="15eba-194">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="15eba-195">См. также</span><span class="sxs-lookup"><span data-stu-id="15eba-195">See also</span></span>

- [<span data-ttu-id="15eba-196">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="15eba-196">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="15eba-197">Классы</span><span class="sxs-lookup"><span data-stu-id="15eba-197">Classes</span></span>](./classes.md)
- [<span data-ttu-id="15eba-198">Структуры</span><span class="sxs-lookup"><span data-stu-id="15eba-198">Structs</span></span>](./structs.md)
- [<span data-ttu-id="15eba-199">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="15eba-199">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="15eba-200">partial (тип)</span><span class="sxs-lookup"><span data-stu-id="15eba-200">partial (Type)</span></span>](../../language-reference/keywords/partial-type.md)
