---
title: "Структуры в C#. Краткий обзор языка C#"
description: "Основная информация о типах значений C# под названием структуры"
keywords: ".NET, C#, структуры,тип значения"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: fa840d80bba98889f75863db2612f196d78bd3c5
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="structs"></a><span data-ttu-id="f4a9a-104">Структуры</span><span class="sxs-lookup"><span data-stu-id="f4a9a-104">Structs</span></span>

<span data-ttu-id="f4a9a-105">Как и классы, ***структуры*** — это сущности для хранения данных, которые могут содержать данные-члены и функции-члены. Но в отличие от классов, структуры являются типами значений и для них не выделяется память из кучи.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-105">Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation.</span></span> <span data-ttu-id="f4a9a-106">Переменная типа структура напрямую хранит все свои данные, а переменная типа класс хранит ссылку на динамически выделяемый объект.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-106">A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object.</span></span> <span data-ttu-id="f4a9a-107">Типы структуры не поддерживают определяемое пользователем наследование. Все типы структуры неявно наследуются от типа <xref:System.ValueType>, который, в свою очередь, неявно наследуется от `object`.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-107">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type <xref:System.ValueType>, which in turn implicitly inherits from `object`.</span></span>

<span data-ttu-id="f4a9a-108">Структуры особенно удобны для небольших структур данных, имеющих семантику значений.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-108">Structs are particularly useful for small data structures that have value semantics.</span></span> <span data-ttu-id="f4a9a-109">Хорошими примерами структур можно считать комплексные числа, точки в системе координат или словари с парами ключ-значение.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-109">Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs.</span></span> <span data-ttu-id="f4a9a-110">Если использовать структуры вместо классов для небольших структур данных, можно существенно снизить количество операций по выделению памяти в приложении.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-110">The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs.</span></span> <span data-ttu-id="f4a9a-111">Например, следующая программа создает и инициализирует массив из 100 точек.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-111">For example, the following program creates and initializes an array of 100 points.</span></span> <span data-ttu-id="f4a9a-112">Если реализовать `Point` как класс, создаются экземпляры для 101 отдельных объектов — один для массива и еще 100 для его элементов.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-112">With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.</span></span>

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

<span data-ttu-id="f4a9a-113">Есть другой вариант — реализовать точки как структуры.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-113">An alternative is to make Point a struct.</span></span>

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

<span data-ttu-id="f4a9a-114">Теперь создается всего один объект (для массива), а экземпляры `Point` хранятся в стеке массива.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-114">Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.</span></span>

<span data-ttu-id="f4a9a-115">Конструктор структур вызывается оператором new, но это не приводит к выделению дополнительной памяти.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-115">Struct constructors are invoked with the new operator, but that does not imply that memory is being allocated.</span></span> <span data-ttu-id="f4a9a-116">Вместо того, чтобы динамически выделять объект и возвращать ссылку на него, конструктор структуры возвращает само значение структуры (обычно сохраняя его во временном расположении в стеке), и затем это значение копируется туда, где оно нужно.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-116">Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.</span></span>

<span data-ttu-id="f4a9a-117">При использовании классов две переменные могут ссылаться на один и тот же объект, поэтому может случиться так, что операции над одной переменной затронут объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-117">With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="f4a9a-118">При использовании структур каждая переменная имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-118">With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other.</span></span> <span data-ttu-id="f4a9a-119">Например, выходные данные следующего фрагмента кода зависят от того, реализованы ли точки как класс или как структура.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-119">For example, the output produced by the following code fragment depends on whether Point is a class or a struct.</span></span>

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

<span data-ttu-id="f4a9a-120">Если `Point` является классом, то возвращается значение 20, поскольку a и b ссылаются на один объект.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-120">If `Point` is a class, the output is 20 because a and b reference the same object.</span></span> <span data-ttu-id="f4a9a-121">Если Point является структурой, возвращается значение 10, поскольку при сохранении `a` в `b` создается копия значения, и это значение не изменяется при последующем присваивании в `a.x`.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-121">If Point is a struct, the output is 10 because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.</span></span>

<span data-ttu-id="f4a9a-122">Предыдущий пример демонстрирует два ограничения, действующие для структур.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-122">The previous example highlights two of the limitations of structs.</span></span> <span data-ttu-id="f4a9a-123">Во-первых, копирование структуры целиком обычно менее эффективно, чем копирование ссылки на объект, поэтому присваивание и передача в качестве параметра потребует больше затрат для структур, чем для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-123">First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types.</span></span> <span data-ttu-id="f4a9a-124">Во-вторых, вы не можете создавать ссылки на структуры (за исключением параметров `in`, `ref` и `out`), что в некоторых ситуациях мешает их применять.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-124">Second, except for `in`, `ref`, and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="f4a9a-125">[Назад](classes-and-objects.md)
[Вперед](arrays.md)</span><span class="sxs-lookup"><span data-stu-id="f4a9a-125">[Previous](classes-and-objects.md)
[Next](arrays.md)</span></span>
