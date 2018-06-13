---
title: Проверочные утверждения (F#)
description: 'Дополнительные сведения о используйте выражение «assert» как средство отладки для тестирования выражений в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 83e6cd77bbbb2c32e9b778e5bf6dd9d2e9c8fe32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563150"
---
# <a name="assertions"></a><span data-ttu-id="5b835-103">Утверждения</span><span class="sxs-lookup"><span data-stu-id="5b835-103">Assertions</span></span>

<span data-ttu-id="5b835-104">`assert` Выражение — это функция отладки, можно использовать для проверки значения выражения.</span><span class="sxs-lookup"><span data-stu-id="5b835-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="5b835-105">При сбое в режиме отладки утверждение создает диалоговое окно системной ошибки.</span><span class="sxs-lookup"><span data-stu-id="5b835-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b835-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b835-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="5b835-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b835-107">Remarks</span></span>

<span data-ttu-id="5b835-108">`assert` Выражение имеет тип `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="5b835-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="5b835-109">В предыдущем синтаксисе *условие* представляет собой логическое выражение, которое необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="5b835-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="5b835-110">Если выражение, результатом которого является `true`, выполнение продолжается без изменений.</span><span class="sxs-lookup"><span data-stu-id="5b835-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="5b835-111">Если значение равно `false`, диалоговое окно ошибки системы.</span><span class="sxs-lookup"><span data-stu-id="5b835-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="5b835-112">Диалоговое окно ошибки имеет заголовок, содержащий строку **ложности**.</span><span class="sxs-lookup"><span data-stu-id="5b835-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="5b835-113">Диалоговое окно содержит трассировку стека, который указывает, где произошел сбой утверждения.</span><span class="sxs-lookup"><span data-stu-id="5b835-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="5b835-114">Проверка утверждений действует только при компиляции в режиме отладки; то есть если константа `DEBUG` определен.</span><span class="sxs-lookup"><span data-stu-id="5b835-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="5b835-115">В системе проекта, по умолчанию `DEBUG` констант определена в конфигурации отладки, но не в конфигурации выпуска.</span><span class="sxs-lookup"><span data-stu-id="5b835-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="5b835-116">Сбой проверочного утверждения нельзя перехватить с помощью обработки исключений в языке F #.</span><span class="sxs-lookup"><span data-stu-id="5b835-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="5b835-117">`assert` Функции разрешается в <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b835-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="5b835-118">Пример</span><span class="sxs-lookup"><span data-stu-id="5b835-118">Example</span></span>

<span data-ttu-id="5b835-119">В следующем примере кода показано использование `assert` выражение.</span><span class="sxs-lookup"><span data-stu-id="5b835-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="5b835-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5b835-120">See Also</span></span>

[<span data-ttu-id="5b835-121">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="5b835-121">F# Language Reference</span></span>](index.md)
