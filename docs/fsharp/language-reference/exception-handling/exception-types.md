---
title: Типы исключений (F#)
description: 'Узнайте, как определить и использовать типы исключений F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4462dd00ddf9524d1fd376ee1e73e81fcfd5d945
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exception-types"></a><span data-ttu-id="ea1ad-103">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="ea1ad-103">Exception Types</span></span>

<span data-ttu-id="ea1ad-104">Существует две категории исключений в языке F #: типы исключений .NET и типы исключений F #.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="ea1ad-105">В этом разделе описывается определение и использование типов исключений F #.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-105">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="ea1ad-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea1ad-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="ea1ad-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea1ad-107">Remarks</span></span>
<span data-ttu-id="ea1ad-108">В предыдущем синтаксисе *тип исключения* имя нового типа исключения F #, и *тип аргумента* представляет тип аргумента, который может быть задан после вызова исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="ea1ad-109">Можно указать несколько аргументов с помощью типа кортежа для *тип аргумента*.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="ea1ad-110">Типичное определение исключения F # выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="ea1ad-111">Исключение этого типа можно создавать с помощью `raise` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="ea1ad-112">Тип исключения F # можно использовать непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="ea1ad-113">Тип исключения, определяемый с `exception` ключевое слово в языке F # — это новый тип, который наследует от `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="ea1ad-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="ea1ad-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ea1ad-114">See Also</span></span>
[<span data-ttu-id="ea1ad-115">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="ea1ad-115">Exception Handling</span></span>](index.md)

[<span data-ttu-id="ea1ad-116">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="ea1ad-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="ea1ad-117">Иерархия исключений</span><span class="sxs-lookup"><span data-stu-id="ea1ad-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
