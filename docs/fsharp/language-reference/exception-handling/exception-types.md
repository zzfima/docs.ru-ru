---
title: Типы исключения
description: Узнайте, как определить и использовать F# типы исключений.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772727"
---
# <a name="exception-types"></a><span data-ttu-id="04cb3-103">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="04cb3-103">Exception Types</span></span>

<span data-ttu-id="04cb3-104">Существует две категории исключений в F#: типы исключений .NET и F# типы исключений.</span><span class="sxs-lookup"><span data-stu-id="04cb3-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="04cb3-105">В этом разделе описывается определение и использование F# типы исключений.</span><span class="sxs-lookup"><span data-stu-id="04cb3-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="04cb3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04cb3-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="04cb3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="04cb3-107">Remarks</span></span>

<span data-ttu-id="04cb3-108">В приведенном выше синтаксисе *тип исключения* имя нового F# тип исключения, и *тип аргумента* представляет тип аргумента, могут быть предоставлены при вызова исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="04cb3-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="04cb3-109">Можно указать несколько аргументов с помощью типа кортежа для *типов аргументов*.</span><span class="sxs-lookup"><span data-stu-id="04cb3-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="04cb3-110">Типичное определение F# исключение имеет следующий вид.</span><span class="sxs-lookup"><span data-stu-id="04cb3-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="04cb3-111">Исключения этого типа можно создать с помощью `raise` функции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="04cb3-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="04cb3-112">Можно использовать F# тип исключения, непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04cb3-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="04cb3-113">Тип исключения, определенный с помощью `exception` ключевое слово в F# — это новый тип, который наследует от `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="04cb3-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="04cb3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="04cb3-114">See also</span></span>

- [<span data-ttu-id="04cb3-115">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="04cb3-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="04cb3-116">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="04cb3-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="04cb3-117">Иерархия исключений</span><span class="sxs-lookup"><span data-stu-id="04cb3-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)