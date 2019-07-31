---
title: Типы исключения
description: Узнайте, как определять и использовать F# типы исключений.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630312"
---
# <a name="exception-types"></a><span data-ttu-id="aaa9d-103">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="aaa9d-103">Exception Types</span></span>

<span data-ttu-id="aaa9d-104">Существует две категории исключений в F#: типы исключений .NET и F# типы исключений.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="aaa9d-105">В этом разделе описывается определение и использование F# типов исключений.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="aaa9d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaa9d-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="aaa9d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaa9d-107">Remarks</span></span>

<span data-ttu-id="aaa9d-108">В предыдущем синтаксисе *Exception-Type* — это имя нового F# типа исключения, а *аргумент-Type* представляет тип аргумента, который может быть указан при вызове исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="aaa9d-109">Можно указать несколько аргументов с помощью типа кортежа для *типа аргумента*.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="aaa9d-110">Типичное определение F# исключения напоминает следующее.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="aaa9d-111">Исключение этого типа можно создать с помощью `raise` функции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="aaa9d-112">Тип F# исключения можно использовать непосредственно в фильтрах в `try...with` выражении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="aaa9d-113">Тип исключения, определяемый с помощью `exception` ключевого слова в F# , является новым типом, который наследует от `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaa9d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aaa9d-114">See also</span></span>

- [<span data-ttu-id="aaa9d-115">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="aaa9d-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="aaa9d-116">Исключения: функция `raise`</span><span class="sxs-lookup"><span data-stu-id="aaa9d-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="aaa9d-117">Иерархия исключений</span><span class="sxs-lookup"><span data-stu-id="aaa9d-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
