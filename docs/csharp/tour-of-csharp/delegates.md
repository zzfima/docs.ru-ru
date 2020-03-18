---
title: Делегаты в C#. Краткий обзор языка C#
description: Информация о позднем связывании с помощью делегатов в C#
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159173"
---
# <a name="delegates"></a><span data-ttu-id="6b25b-103">Делегаты</span><span class="sxs-lookup"><span data-stu-id="6b25b-103">Delegates</span></span>

<span data-ttu-id="6b25b-104">***Тип delegate*** представляет ссылки на методы с конкретным списком параметров и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="6b25b-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="6b25b-105">Делегаты позволяют использовать методы как сущности, сохраняя их в переменные и передавая в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="6b25b-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="6b25b-106">Принцип работы делегатов близок к указателям функций из некоторых языков.</span><span class="sxs-lookup"><span data-stu-id="6b25b-106">Delegates are similar to the concept of function pointers found in some other languages.</span></span> <span data-ttu-id="6b25b-107">В отличие от указателей функций, делегаты являются объектно-ориентированными и типобезопасными.</span><span class="sxs-lookup"><span data-stu-id="6b25b-107">Unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="6b25b-108">Следующий пример кода объявляет и использует тип делегата с именем `Function`.</span><span class="sxs-lookup"><span data-stu-id="6b25b-108">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="6b25b-109">Экземпляр `Function` с типом делегата может ссылаться на любой метод, который принимает аргумент `double` и возвращает значение `double`.</span><span class="sxs-lookup"><span data-stu-id="6b25b-109">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="6b25b-110">Метод `Apply` применяет заданную функцию к элементам `double[]` и возвращает `double[]` с результатами.</span><span class="sxs-lookup"><span data-stu-id="6b25b-110">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="6b25b-111">В методе `Main` используется `Apply` для применения трех различных функций к `double[]`.</span><span class="sxs-lookup"><span data-stu-id="6b25b-111">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="6b25b-112">Делегат может ссылаться на статический метод (например, `Square` или `Math.Sin` в предыдущем примере) или метод экземпляра (например, `m.Multiply` в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="6b25b-112">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="6b25b-113">Делегат, который ссылается на метод экземпляра, также содержит ссылку на конкретный объект. Когда метод экземпляра вызывается через делегат, этот объект превращается в `this` в вызове.</span><span class="sxs-lookup"><span data-stu-id="6b25b-113">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="6b25b-114">Делегаты могут также создаваться с использованием анонимных функций, то есть создаваемых при объявлении "встроенных методов".</span><span class="sxs-lookup"><span data-stu-id="6b25b-114">Delegates can also be created using anonymous functions, which are "inline methods" that are created when declared.</span></span> <span data-ttu-id="6b25b-115">Анонимные функции могут использовать локальные переменные соседних методов.</span><span class="sxs-lookup"><span data-stu-id="6b25b-115">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="6b25b-116">В следующем примере не создается класс:</span><span class="sxs-lookup"><span data-stu-id="6b25b-116">The following example doesn't create a class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="6b25b-117">Делегат не имеет информации или ограничений в отношении того, к какому классу относится метод, на который он ссылается. Достаточно лишь, чтобы метод, на который указывает ссылка, имел такие же параметры и тип возвращаемого значения, что и делегат.</span><span class="sxs-lookup"><span data-stu-id="6b25b-117">A delegate doesn't know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6b25b-118">[Назад](interfaces.md)
>[Вперед](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="6b25b-118">[Previous](interfaces.md)
[Next](attributes.md)</span></span>
