---
title: Циклы. Выражение for...to
description: См. раздел F# о... выражение to используется для прохода по циклу над диапазоном значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626623"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="85edd-103">Циклы. Выражение for...to</span><span class="sxs-lookup"><span data-stu-id="85edd-103">Loops: for...to Expression</span></span>

<span data-ttu-id="85edd-104">`for...to` Выражение используется для прохода по циклу над диапазоном значений переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="85edd-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="85edd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85edd-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="85edd-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="85edd-106">Remarks</span></span>

<span data-ttu-id="85edd-107">Тип идентификатора выводится из типа выражений *начала* и *окончания* .</span><span class="sxs-lookup"><span data-stu-id="85edd-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="85edd-108">Типы для этих выражений должны быть 32-разрядными целыми числами.</span><span class="sxs-lookup"><span data-stu-id="85edd-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="85edd-109">Хотя технически это выражение, `for...to` более похоже на традиционный оператор в императивном языке программирования.</span><span class="sxs-lookup"><span data-stu-id="85edd-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="85edd-110">Тип возвращаемого значения для *выражения тела* должен быть `unit`.</span><span class="sxs-lookup"><span data-stu-id="85edd-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="85edd-111">В следующих примерах показаны различные варианты использования `for...to` выражения.</span><span class="sxs-lookup"><span data-stu-id="85edd-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="85edd-112">Результат выполнения приведенного кода будет следующим.</span><span class="sxs-lookup"><span data-stu-id="85edd-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="85edd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="85edd-113">See also</span></span>

- [<span data-ttu-id="85edd-114">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="85edd-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="85edd-115">Бираются `for...in`Выражение</span><span class="sxs-lookup"><span data-stu-id="85edd-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="85edd-116">Бираются `while...do`Выражение</span><span class="sxs-lookup"><span data-stu-id="85edd-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
