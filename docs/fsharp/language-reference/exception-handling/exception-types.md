---
title: Типы исключений (F#)
description: 'Узнайте, как определить и использовать типы исключений F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858825"
---
# <a name="exception-types"></a><span data-ttu-id="c0cb4-103">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="c0cb4-103">Exception Types</span></span>

<span data-ttu-id="c0cb4-104">Существует две категории исключений в языке F #: типы исключений .NET и типы исключений F #.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="c0cb4-105">В этом разделе описывается определение и использование типов исключений F #.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0cb4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0cb4-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="c0cb4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0cb4-107">Remarks</span></span>

<span data-ttu-id="c0cb4-108">В приведенном выше синтаксисе *тип исключения* имя нового типа исключения F #, и *тип аргумента* представляет тип аргумента, могут быть предоставлены при вызова исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="c0cb4-109">Можно указать несколько аргументов с помощью типа кортежа для *типов аргументов*.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="c0cb4-110">Типичное определение исключения F # выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="c0cb4-111">Исключения этого типа можно создать с помощью `raise` функции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="c0cb4-112">Тип исключения F # можно использовать непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="c0cb4-113">Тип исключения, определенный с помощью `exception` ключевое слово в F # — это новый тип, который наследует от `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="c0cb4-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0cb4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c0cb4-114">See also</span></span>

- [<span data-ttu-id="c0cb4-115">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="c0cb4-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="c0cb4-116">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="c0cb4-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="c0cb4-117">Иерархия исключений</span><span class="sxs-lookup"><span data-stu-id="c0cb4-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
