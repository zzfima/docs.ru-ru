---
title: "Явная реализация интерфейса (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6baf985e8031e1e859d20570168222ca8f368eff
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="c46cf-102">Явная реализация интерфейса (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="c46cf-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="c46cf-103">Если [класс](../../../csharp/language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, при реализации такого члена в классе оба интерфейса будут использовать этот член в качестве собственной реализации.</span><span class="sxs-lookup"><span data-stu-id="c46cf-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="c46cf-104">В следующем примере все вызовы `Paint` приводят к вызову одного и того же метода.</span><span class="sxs-lookup"><span data-stu-id="c46cf-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 <span data-ttu-id="c46cf-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46cf-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span></span>  
  
 <span data-ttu-id="c46cf-106">Если два члена [интерфейса](../../../csharp/language-reference/keywords/interface.md) выполняют разные функции, это может привести к некорректной реализации одного или обоих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="c46cf-106">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="c46cf-107">Член интерфейса можно реализовать явно, создав член класса, который вызывается только через этот интерфейс и относится только к нему.</span><span class="sxs-lookup"><span data-stu-id="c46cf-107">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="c46cf-108">Для этого в имени члена класса указывается имя интерфейса, после которого следует точка.</span><span class="sxs-lookup"><span data-stu-id="c46cf-108">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="c46cf-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="c46cf-109">For example:</span></span>  
  
 <span data-ttu-id="c46cf-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46cf-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span></span>  
  
 <span data-ttu-id="c46cf-111">Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а `ISurface.Paint` — только через интерфейс `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="c46cf-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="c46cf-112">Обе реализации метода будут разделены, и ни одна из них не будет доступна в классе напрямую.</span><span class="sxs-lookup"><span data-stu-id="c46cf-112">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="c46cf-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="c46cf-113">For example:</span></span>  
  
 <span data-ttu-id="c46cf-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46cf-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span></span>  
  
 <span data-ttu-id="c46cf-115">Явная реализация также применяется в случаях, когда в каждом из двух интерфейсов объявляются разные члены (например, свойство и метод) с одинаковыми именами:</span><span class="sxs-lookup"><span data-stu-id="c46cf-115">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 <span data-ttu-id="c46cf-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46cf-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span></span>  
  
 <span data-ttu-id="c46cf-117">Чтобы реализовать оба интерфейса и избежать ошибок компилятора, класс должен использовать явную реализацию либо свойства P, либо метода P, либо одновременно обоих этих членов.</span><span class="sxs-lookup"><span data-stu-id="c46cf-117">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="c46cf-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="c46cf-118">For example:</span></span>  
  
 <span data-ttu-id="c46cf-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46cf-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46cf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c46cf-120">See Also</span></span>  
 <span data-ttu-id="c46cf-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c46cf-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c46cf-122">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="c46cf-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="c46cf-123">[Интерфейсы](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="c46cf-123">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="c46cf-124">Наследование</span><span class="sxs-lookup"><span data-stu-id="c46cf-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

