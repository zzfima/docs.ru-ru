---
title: Делегаты (F#)
description: 'Узнайте, как работать с делегатами в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 664b4f80302871d05ea9604ca90219e19bc14ddb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="delegates"></a><span data-ttu-id="8a94e-103">Делегаты</span><span class="sxs-lookup"><span data-stu-id="8a94e-103">Delegates</span></span>

<span data-ttu-id="8a94e-104">Делегат представляет вызов функции в виде объекта.</span><span class="sxs-lookup"><span data-stu-id="8a94e-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="8a94e-105">В F # обычно следует использовать значения функций для представления функции как значения первого класса; Тем не менее делегаты используются в .NET Framework и поэтому они необходимы при взаимодействии с API, ожидающих их.</span><span class="sxs-lookup"><span data-stu-id="8a94e-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="8a94e-106">Они могут использоваться при создании библиотек, предназначенных для использования в других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a94e-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="8a94e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a94e-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="8a94e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a94e-108">Remarks</span></span>
<span data-ttu-id="8a94e-109">В предыдущем синтаксисе `type1` представляет аргумент типа или типов и `type2` представляет тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="8a94e-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="8a94e-110">Типы аргументов, которые представляются `type1` каррированные автоматически.</span><span class="sxs-lookup"><span data-stu-id="8a94e-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="8a94e-111">Таким образом, для этого типа используется кортеже, если аргументы целевой функции каррированные и в кортеже аргументы, которые уже находятся в кортеже.</span><span class="sxs-lookup"><span data-stu-id="8a94e-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="8a94e-112">Автоматическое каррирование удаляет круглые скобки, оставляя аргумент в виде кортежа, соответствующий целевому методу.</span><span class="sxs-lookup"><span data-stu-id="8a94e-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="8a94e-113">См. в примере кода для синтаксиса, который следует использовать в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="8a94e-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="8a94e-114">Делегаты можно подключить к значений функции F # и статические или методов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8a94e-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="8a94e-115">Значения функции F # можно передать непосредственно как аргументы конструкторам делегатов.</span><span class="sxs-lookup"><span data-stu-id="8a94e-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="8a94e-116">Для статического метода делегат создается с помощью имени класса и метода.</span><span class="sxs-lookup"><span data-stu-id="8a94e-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="8a94e-117">Для метода экземпляра необходимо предоставить экземпляр объекта и метода в один аргумент.</span><span class="sxs-lookup"><span data-stu-id="8a94e-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="8a94e-118">В обоих случаях оператор доступа к члену (`.`) используется.</span><span class="sxs-lookup"><span data-stu-id="8a94e-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="8a94e-119">`Invoke` Метод для типа делегата вызывает инкапсулированную функцию.</span><span class="sxs-lookup"><span data-stu-id="8a94e-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="8a94e-120">Кроме того делегаты могут передаваться как значения функции, ссылаясь на имя метода Invoke без круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="8a94e-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="8a94e-121">Ниже приведен синтаксис для создания делегатов, представляющих различные методы в классе.</span><span class="sxs-lookup"><span data-stu-id="8a94e-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="8a94e-122">В зависимости от того, является ли метод статический метод или метод экземпляра, а наличие аргументов в кортеже или каррированные синтаксис для объявления и назначения делегата немного отличается.</span><span class="sxs-lookup"><span data-stu-id="8a94e-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="8a94e-123">В следующем коде показано несколько способов работы с делегатами.</span><span class="sxs-lookup"><span data-stu-id="8a94e-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="8a94e-124">В предыдущем примере кода выводится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="8a94e-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="8a94e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8a94e-125">See Also</span></span>
[<span data-ttu-id="8a94e-126">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="8a94e-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8a94e-127">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="8a94e-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="8a94e-128">События</span><span class="sxs-lookup"><span data-stu-id="8a94e-128">Events</span></span>](members/events.md)
