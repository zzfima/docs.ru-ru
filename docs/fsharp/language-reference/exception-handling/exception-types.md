---
title: "Типы исключений (F#)"
description: "Узнайте, как определить и использовать типы исключений F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a><span data-ttu-id="3334a-104">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="3334a-104">Exception Types</span></span>

<span data-ttu-id="3334a-105">Существует две категории исключений в языке F #: типы исключений .NET и типы исключений F #.</span><span class="sxs-lookup"><span data-stu-id="3334a-105">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="3334a-106">В этом разделе описывается определение и использование типов исключений F #.</span><span class="sxs-lookup"><span data-stu-id="3334a-106">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="3334a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3334a-107">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="3334a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3334a-108">Remarks</span></span>
<span data-ttu-id="3334a-109">В предыдущем синтаксисе *тип исключения* имя нового типа исключения F #, и *тип аргумента* представляет тип аргумента, который может быть задан после вызова исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="3334a-109">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="3334a-110">Можно указать несколько аргументов с помощью типа кортежа для *тип аргумента*.</span><span class="sxs-lookup"><span data-stu-id="3334a-110">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="3334a-111">Типичное определение исключения F # выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3334a-111">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="3334a-112">Исключение этого типа можно создавать с помощью `raise` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3334a-112">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="3334a-113">Тип исключения F # можно использовать непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3334a-113">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="3334a-114">Тип исключения, определяемый с `exception` ключевое слово в языке F # — это новый тип, который наследует от `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="3334a-114">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="3334a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3334a-115">See Also</span></span>
[<span data-ttu-id="3334a-116">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="3334a-116">Exception Handling</span></span>](index.md)

[<span data-ttu-id="3334a-117">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="3334a-117">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="3334a-118">Иерархия исключений</span><span class="sxs-lookup"><span data-stu-id="3334a-118">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
