---
title: "Делегаты (F#)"
description: "Узнайте, как работать с делегатами в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a><span data-ttu-id="50fc9-104">Делегаты</span><span class="sxs-lookup"><span data-stu-id="50fc9-104">Delegates</span></span>

<span data-ttu-id="50fc9-105">Делегат представляет вызов функции в виде объекта.</span><span class="sxs-lookup"><span data-stu-id="50fc9-105">A delegate represents a function call as an object.</span></span> <span data-ttu-id="50fc9-106">В F # обычно следует использовать значения функций для представления функции как значения первого класса; Тем не менее делегаты используются в .NET Framework и поэтому они необходимы при взаимодействии с API, ожидающих их.</span><span class="sxs-lookup"><span data-stu-id="50fc9-106">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="50fc9-107">Они могут использоваться при создании библиотек, предназначенных для использования в других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50fc9-107">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="50fc9-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50fc9-108">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="50fc9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="50fc9-109">Remarks</span></span>
<span data-ttu-id="50fc9-110">В предыдущем синтаксисе `type1` представляет аргумент типа или типов и `type2` представляет тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="50fc9-110">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="50fc9-111">Типы аргументов, которые представляются `type1` каррированные автоматически.</span><span class="sxs-lookup"><span data-stu-id="50fc9-111">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="50fc9-112">Таким образом, для этого типа используется кортеже, если аргументы целевой функции каррированные и в кортеже аргументы, которые уже находятся в кортеже.</span><span class="sxs-lookup"><span data-stu-id="50fc9-112">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="50fc9-113">Автоматическое каррирование удаляет круглые скобки, оставляя аргумент в виде кортежа, соответствующий целевому методу.</span><span class="sxs-lookup"><span data-stu-id="50fc9-113">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="50fc9-114">См. в примере кода для синтаксиса, который следует использовать в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="50fc9-114">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="50fc9-115">Делегаты можно подключить к значений функции F # и статические или методов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="50fc9-115">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="50fc9-116">Значения функции F # можно передать непосредственно как аргументы конструкторам делегатов.</span><span class="sxs-lookup"><span data-stu-id="50fc9-116">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="50fc9-117">Для статического метода делегат создается с помощью имени класса и метода.</span><span class="sxs-lookup"><span data-stu-id="50fc9-117">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="50fc9-118">Для метода экземпляра необходимо предоставить экземпляр объекта и метода в один аргумент.</span><span class="sxs-lookup"><span data-stu-id="50fc9-118">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="50fc9-119">В обоих случаях оператор доступа к члену (`.`) используется.</span><span class="sxs-lookup"><span data-stu-id="50fc9-119">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="50fc9-120">`Invoke` Метод для типа делегата вызывает инкапсулированную функцию.</span><span class="sxs-lookup"><span data-stu-id="50fc9-120">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="50fc9-121">Кроме того делегаты могут передаваться как значения функции, ссылаясь на имя метода Invoke без круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="50fc9-121">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="50fc9-122">Ниже приведен синтаксис для создания делегатов, представляющих различные методы в классе.</span><span class="sxs-lookup"><span data-stu-id="50fc9-122">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="50fc9-123">В зависимости от того, является ли метод статический метод или метод экземпляра, а наличие аргументов в кортеже или каррированные синтаксис для объявления и назначения делегата немного отличается.</span><span class="sxs-lookup"><span data-stu-id="50fc9-123">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="50fc9-124">В следующем коде показано несколько способов работы с делегатами.</span><span class="sxs-lookup"><span data-stu-id="50fc9-124">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="50fc9-125">В предыдущем примере кода выводится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="50fc9-125">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="50fc9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="50fc9-126">See Also</span></span>
[<span data-ttu-id="50fc9-127">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="50fc9-127">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="50fc9-128">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="50fc9-128">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="50fc9-129">События</span><span class="sxs-lookup"><span data-stu-id="50fc9-129">Events</span></span>](members/events.md)
