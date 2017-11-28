---
title: "Делегаты в C#. Краткий обзор языка C#"
description: "Информация о позднем связывании с помощью делегатов в C#"
keywords: ".NET, c#, делегат, лямбда-выражения, позднее связывание"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: bb304b2e5c762a44aab931b5e8f7fe9c99805eba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a><span data-ttu-id="d4898-104">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d4898-104">Delegates</span></span>

<span data-ttu-id="d4898-105">***Тип delegate*** представляет ссылки на методы с конкретным списком параметров и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d4898-105">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="d4898-106">Делегаты позволяют использовать методы как сущности, сохраняя их в переменные и передавая в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="d4898-106">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="d4898-107">Принцип работы делегатов близок к указателям функций из некоторых языков, но в отличие от указателей функций делегаты являются объектно-ориентированными и строго типизированными.</span><span class="sxs-lookup"><span data-stu-id="d4898-107">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="d4898-108">Следующий пример кода объявляет и использует тип делегата с именем `Function`.</span><span class="sxs-lookup"><span data-stu-id="d4898-108">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="d4898-109">Экземпляр `Function` с типом делегата может ссылаться на любой метод, который принимает аргумент `double` и возвращает значение `double`.</span><span class="sxs-lookup"><span data-stu-id="d4898-109">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="d4898-110">Метод `Apply` применяет заданную функцию к элементам `double[]` и возвращает `double[]` с результатами.</span><span class="sxs-lookup"><span data-stu-id="d4898-110">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="d4898-111">В методе `Main` используется `Apply` для применения трех различных функций к `double[]`.</span><span class="sxs-lookup"><span data-stu-id="d4898-111">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="d4898-112">Делегат может ссылаться на статический метод (например, `Square` или `Math.Sin` в предыдущем примере) или метод экземпляра (например, `m.Multiply` в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="d4898-112">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="d4898-113">Делегат, который ссылается на метод экземпляра, также содержит ссылку на конкретный объект. Когда метод экземпляра вызывается через делегат, этот объект превращается в `this` в вызове.</span><span class="sxs-lookup"><span data-stu-id="d4898-113">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="d4898-114">Делегаты могут также создаваться с использованием анонимных функций, то есть создаваемых на ходу "встроенных методов".</span><span class="sxs-lookup"><span data-stu-id="d4898-114">Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly.</span></span> <span data-ttu-id="d4898-115">Анонимные функции могут использовать локальные переменные соседних методов.</span><span class="sxs-lookup"><span data-stu-id="d4898-115">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="d4898-116">Таким образом, приведенный выше пример умножения можно записать проще и без использования класса множителя:</span><span class="sxs-lookup"><span data-stu-id="d4898-116">Thus, the multiplier example above can be written more easily without using a Multiplier class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="d4898-117">Также стоит упомянуть о такой интересной и полезной особенности делегата, что он не имеет информации или ограничений в отношении того, к какому классу относится указанный в нем метод. Достаточно лишь, чтобы указанный метод имел такие же типы параметров и возвращаемого значения, которые назначены для делегата.</span><span class="sxs-lookup"><span data-stu-id="d4898-117">An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d4898-118">[Назад](enums.md)
[Вперед](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="d4898-118">[Previous](enums.md)
[Next](attributes.md)</span></span>
