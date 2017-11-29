---
title: "Явная реализация интерфейса (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b746a69484b73a4212c729e02a1256ee1c83ea41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="7e32a-102">Явная реализация интерфейса (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="7e32a-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="7e32a-103">Если [класс](../../../csharp/language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, при реализации такого члена в классе оба интерфейса будут использовать этот член в качестве собственной реализации.</span><span class="sxs-lookup"><span data-stu-id="7e32a-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="7e32a-104">В следующем примере все вызовы `Paint` приводят к вызову одного и того же метода.</span><span class="sxs-lookup"><span data-stu-id="7e32a-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 <span data-ttu-id="7e32a-105">Если два члена [интерфейса](../../../csharp/language-reference/keywords/interface.md) выполняют разные функции, это может привести к некорректной реализации одного или обоих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="7e32a-105">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="7e32a-106">Член интерфейса можно реализовать явно, создав член класса, который вызывается только через этот интерфейс и относится только к нему.</span><span class="sxs-lookup"><span data-stu-id="7e32a-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="7e32a-107">Для этого в имени члена класса указывается имя интерфейса, после которого следует точка.</span><span class="sxs-lookup"><span data-stu-id="7e32a-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="7e32a-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="7e32a-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 <span data-ttu-id="7e32a-109">Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а `ISurface.Paint` — только через интерфейс `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="7e32a-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="7e32a-110">Обе реализации метода будут разделены, и ни одна из них не будет доступна в классе напрямую.</span><span class="sxs-lookup"><span data-stu-id="7e32a-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="7e32a-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="7e32a-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 <span data-ttu-id="7e32a-112">Явная реализация также применяется в случаях, когда в каждом из двух интерфейсов объявляются разные члены (например, свойство и метод) с одинаковыми именами:</span><span class="sxs-lookup"><span data-stu-id="7e32a-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 <span data-ttu-id="7e32a-113">Чтобы реализовать оба интерфейса и избежать ошибок компилятора, класс должен использовать явную реализацию либо свойства P, либо метода P, либо одновременно обоих этих членов.</span><span class="sxs-lookup"><span data-stu-id="7e32a-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="7e32a-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="7e32a-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7e32a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7e32a-115">See Also</span></span>  
 [<span data-ttu-id="7e32a-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7e32a-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7e32a-117">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="7e32a-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="7e32a-118">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="7e32a-118">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="7e32a-119">Наследование</span><span class="sxs-lookup"><span data-stu-id="7e32a-119">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
