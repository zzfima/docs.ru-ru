---
title: Руководство по программированию на C#. Явная реализация интерфейса
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628154"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="66c36-102">Явная реализация интерфейса (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="66c36-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="66c36-103">Если [класс](../../language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, при реализации такого члена в классе оба интерфейса будут использовать этот член в качестве собственной реализации.</span><span class="sxs-lookup"><span data-stu-id="66c36-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="66c36-104">В следующем примере все вызовы `Paint` приводят к вызову одного и того же метода.</span><span class="sxs-lookup"><span data-stu-id="66c36-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="66c36-105">Первый пример определяет типы:</span><span class="sxs-lookup"><span data-stu-id="66c36-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="66c36-106">Следующий пример вызывает методы:</span><span class="sxs-lookup"><span data-stu-id="66c36-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="66c36-107">Если два члена интерфейса выполняют разные функции, это может привести к некорректной реализации одного или обоих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="66c36-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="66c36-108">Член интерфейса можно реализовать явно, создав член класса, который вызывается только через этот интерфейс и относится только к нему.</span><span class="sxs-lookup"><span data-stu-id="66c36-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="66c36-109">Укажите в имени члена класса имя интерфейса и точку.</span><span class="sxs-lookup"><span data-stu-id="66c36-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="66c36-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="66c36-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="66c36-111">Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а `ISurface.Paint` — только через интерфейс `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="66c36-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="66c36-112">Обе реализации метода будут разделены, и ни одна из них не будет доступна в классе напрямую.</span><span class="sxs-lookup"><span data-stu-id="66c36-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="66c36-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="66c36-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="66c36-114">Явная реализация также применяется в случаях, когда в каждом из двух интерфейсов объявляются разные члены (например, свойство и метод) с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="66c36-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="66c36-115">Чтобы реализовать оба интерфейса и избежать ошибок компилятора, класс должен использовать явную реализацию либо свойства `P`, либо метода `P`, либо одновременно обоих этих членов.</span><span class="sxs-lookup"><span data-stu-id="66c36-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="66c36-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="66c36-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="66c36-117">Если класс наследует реализацию метода от интерфейса, этот метод доступен только через ссылку типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="66c36-117">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="66c36-118">Наследуемый член не отображается как часть открытого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="66c36-118">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="66c36-119">Следующий пример определяет реализацию по умолчанию для метода интерфейса:</span><span class="sxs-lookup"><span data-stu-id="66c36-119">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="66c36-120">Следующий пример вызывает реализацию по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="66c36-120">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="66c36-121">Любой класс, реализующий интерфейс `IControl`, может переопределить метод `Paint` по умолчанию либо в качестве открытого метода, либо в качестве реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="66c36-121">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="66c36-122">См. также</span><span class="sxs-lookup"><span data-stu-id="66c36-122">See also</span></span>

- [<span data-ttu-id="66c36-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="66c36-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="66c36-124">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="66c36-124">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="66c36-125">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="66c36-125">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="66c36-126">Наследование</span><span class="sxs-lookup"><span data-stu-id="66c36-126">Inheritance</span></span>](../classes-and-structs/inheritance.md)
