---
title: Утверждения
description: Узнайте, как использовать выражение "Assert" в качестве функции отладки для тестирования выражений на языке F# программирования.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799063"
---
# <a name="assertions"></a><span data-ttu-id="2c292-103">Утверждения</span><span class="sxs-lookup"><span data-stu-id="2c292-103">Assertions</span></span>

<span data-ttu-id="2c292-104">Выражение `assert` — это функция отладки, которую можно использовать для проверки выражения.</span><span class="sxs-lookup"><span data-stu-id="2c292-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="2c292-105">При сбое в режиме отладки утверждение создает диалоговое окно системной ошибки.</span><span class="sxs-lookup"><span data-stu-id="2c292-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c292-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c292-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="2c292-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="2c292-107">Remarks</span></span>

<span data-ttu-id="2c292-108">Выражение `assert` имеет тип `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="2c292-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="2c292-109">Функция `assert` разрешается в <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c292-109">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c292-110">Это означает, что его поведение аналогично вызову <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> напрямую.</span><span class="sxs-lookup"><span data-stu-id="2c292-110">This means its behavior is identical to having called <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="2c292-111">Проверка утверждения включена только при компиляции в режиме отладки. то есть, если определена константа `DEBUG`.</span><span class="sxs-lookup"><span data-stu-id="2c292-111">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="2c292-112">В системе проекта по умолчанию константа `DEBUG` определена в конфигурации отладки, но не в конфигурации выпуска.</span><span class="sxs-lookup"><span data-stu-id="2c292-112">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="2c292-113">Ошибка при сбое утверждения не может быть перехвачена с F# помощью обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="2c292-113">The assertion failure error cannot be caught by using F# exception handling.</span></span>

## <a name="example"></a><span data-ttu-id="2c292-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2c292-114">Example</span></span>

<span data-ttu-id="2c292-115">В следующем примере кода показано использование выражения `assert`.</span><span class="sxs-lookup"><span data-stu-id="2c292-115">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="2c292-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2c292-116">See also</span></span>

- [<span data-ttu-id="2c292-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="2c292-117">F# Language Reference</span></span>](index.md)
