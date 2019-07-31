---
title: Делегаты
description: Узнайте, как работать с делегатами F#в.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630368"
---
# <a name="delegates"></a><span data-ttu-id="7f92a-103">Делегаты</span><span class="sxs-lookup"><span data-stu-id="7f92a-103">Delegates</span></span>

<span data-ttu-id="7f92a-104">Делегат представляет вызов функции как объект.</span><span class="sxs-lookup"><span data-stu-id="7f92a-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="7f92a-105">В F#обычно значения функций следует использовать для представления функций в качестве значений первого класса; Однако делегаты используются в .NET Framework и поэтому необходимы при взаимодействии с интерфейсами API, ожидающими их.</span><span class="sxs-lookup"><span data-stu-id="7f92a-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="7f92a-106">Их также можно использовать при создании библиотек, предназначенных для использования на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f92a-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f92a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f92a-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="7f92a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f92a-108">Remarks</span></span>

<span data-ttu-id="7f92a-109">В предыдущем синтаксисе `type1` представляет тип аргумента или типы и `type2` представляет тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7f92a-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="7f92a-110">Типы аргументов, представленные `type1` , автоматически являются каррированных.</span><span class="sxs-lookup"><span data-stu-id="7f92a-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="7f92a-111">Это предполагает, что для этого типа используется форма кортежа, если аргументы целевой функции являются переданными, и кортеж в круглых скобках для аргументов, которые уже находятся в форме кортежа.</span><span class="sxs-lookup"><span data-stu-id="7f92a-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="7f92a-112">Автоматически карринг удаляет набор круглых скобок, в результате чего остается аргумент кортежа, соответствующий целевому методу.</span><span class="sxs-lookup"><span data-stu-id="7f92a-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="7f92a-113">Синтаксис, который следует использовать в каждом случае, см. в примере кода.</span><span class="sxs-lookup"><span data-stu-id="7f92a-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="7f92a-114">Делегаты можно прикреплять F# к значениям функций, статическим или методам экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7f92a-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="7f92a-115">F#значения функций могут передаваться непосредственно в качестве аргументов конструкторам делегатов.</span><span class="sxs-lookup"><span data-stu-id="7f92a-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="7f92a-116">Для статического метода делегат создается с помощью имени класса и метода.</span><span class="sxs-lookup"><span data-stu-id="7f92a-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="7f92a-117">Для метода экземпляра вы предоставляете экземпляр объекта и метод в одном аргументе.</span><span class="sxs-lookup"><span data-stu-id="7f92a-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="7f92a-118">В обоих случаях используется оператор доступа к членам (`.`).</span><span class="sxs-lookup"><span data-stu-id="7f92a-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="7f92a-119">`Invoke` Метод в типе делегата вызывает инкапсулированную функцию.</span><span class="sxs-lookup"><span data-stu-id="7f92a-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="7f92a-120">Кроме того, делегаты можно передавать как значения функций, ссылаясь на имя метода Invoke без скобок.</span><span class="sxs-lookup"><span data-stu-id="7f92a-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="7f92a-121">В следующем коде показан синтаксис для создания делегатов, представляющих различные методы в классе.</span><span class="sxs-lookup"><span data-stu-id="7f92a-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="7f92a-122">В зависимости от того, является ли метод статическим методом или методом экземпляра и имеет ли он аргументы в форме кортежа или в каррированных форме, синтаксис объявления и присваивания делегата немного отличается.</span><span class="sxs-lookup"><span data-stu-id="7f92a-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="7f92a-123">В следующем коде показаны различные способы работы с делегатами.</span><span class="sxs-lookup"><span data-stu-id="7f92a-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="7f92a-124">Выходные данные предыдущего примера кода выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7f92a-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="7f92a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7f92a-125">See also</span></span>

- [<span data-ttu-id="7f92a-126">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="7f92a-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7f92a-127">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="7f92a-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="7f92a-128">События</span><span class="sxs-lookup"><span data-stu-id="7f92a-128">Events</span></span>](./members/events.md)
