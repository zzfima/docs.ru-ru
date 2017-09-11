---
title: "Оператор using (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: 201dde951b4f92d92b7d78b3d71a3f3cfb559507
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-statement-c-reference"></a><span data-ttu-id="274b4-102">Оператор using (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="274b4-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="274b4-103">Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="274b4-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="274b4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="274b4-104">Example</span></span>  
 <span data-ttu-id="274b4-105">В следующем примере показано, как использовать оператор using.</span><span class="sxs-lookup"><span data-stu-id="274b4-105">The following example shows how to use the using statement.</span></span>  
  
 <span data-ttu-id="274b4-106">[!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="274b4-106">[!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="274b4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="274b4-107">Remarks</span></span>  
 <span data-ttu-id="274b4-108"><xref:System.IO.File> и <xref:System.Drawing.Font> представляют собой примеры управляемых типов, которые обращаются к неуправляемым ресурсам (в данном случае это обработчики файлов и контексты устройств).</span><span class="sxs-lookup"><span data-stu-id="274b4-108"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="274b4-109">Существуют и многие другие виды неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют.</span><span class="sxs-lookup"><span data-stu-id="274b4-109">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="274b4-110">Все эти типы реализуют интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="274b4-110">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
 <span data-ttu-id="274b4-111">Как правило, при использовании объекта `IDisposable` его следует объявить в операторе `using` и создать в нем его экземпляр.</span><span class="sxs-lookup"><span data-stu-id="274b4-111">As a rule, when you use an `IDisposable` object, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="274b4-112">Оператор `using` правильно вызывает метод <xref:System.IDisposable.Dispose%2A> для объектов, а также (если он используется, как показано выше) становится причиной выхода объекта из области действия, как только вызывается метод <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="274b4-112">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="274b4-113">В блоке `using` объект доступен только для чтения, и изменить или переназначить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="274b4-113">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="274b4-114">Оператор `using` обеспечивает вызов метода <xref:System.IDisposable.Dispose%2A>, даже если при вызове методов для соответствующего объекта возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="274b4-114">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="274b4-115">Тот же результат можно получить, поместив объект в блок try, а затем вызвав метод <xref:System.IDisposable.Dispose%2A> в блоке finally; фактически компилятор переводит оператор `using` именно так.</span><span class="sxs-lookup"><span data-stu-id="274b4-115">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="274b4-116">Во время компиляции представленный выше код разворачивается в следующий (обратите внимание на дополнительные фигурные скобки, создающие ограниченную область действия для объекта):</span><span class="sxs-lookup"><span data-stu-id="274b4-116">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 <span data-ttu-id="274b4-117">[!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="274b4-117">[!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]</span></span>  
  
 <span data-ttu-id="274b4-118">В операторе `using` можно объявить сразу несколько экземпляров типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="274b4-118">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 <span data-ttu-id="274b4-119">[!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="274b4-119">[!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]</span></span>  
  
 <span data-ttu-id="274b4-120">Вы можете создать экземпляр объекта ресурсов, а затем передать переменную в оператор `using`, однако делать этого не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="274b4-120">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="274b4-121">В этом случае объект остается в области действия и после того, как блок `using` теряет контроль, несмотря на то, что доступа к неуправляемым ресурсам у него, скорее всего, не будет.</span><span class="sxs-lookup"><span data-stu-id="274b4-121">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="274b4-122">Другими словами, он больше не будет полностью инициализирован.</span><span class="sxs-lookup"><span data-stu-id="274b4-122">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="274b4-123">При попытке использовать объект за пределами блока `using` может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="274b4-123">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="274b4-124">По этой причине лучше создать экземпляр объекта в операторе `using` и ограничить область действия блоком `using`.</span><span class="sxs-lookup"><span data-stu-id="274b4-124">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 <span data-ttu-id="274b4-125">[!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="274b4-125">[!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="274b4-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="274b4-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="274b4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="274b4-127">See Also</span></span>  
 <span data-ttu-id="274b4-128">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="274b4-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="274b4-129">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="274b4-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="274b4-130">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="274b4-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="274b4-131">[Директива using](../../../csharp/language-reference/keywords/using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="274b4-131">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="274b4-132">[Сборка мусора](../../../standard/garbage-collection/index.md) </span><span class="sxs-lookup"><span data-stu-id="274b4-132">[Garbage Collection](../../../standard/garbage-collection/index.md) </span></span>  
 [<span data-ttu-id="274b4-133">Реализация метода dispose</span><span class="sxs-lookup"><span data-stu-id="274b4-133">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)

