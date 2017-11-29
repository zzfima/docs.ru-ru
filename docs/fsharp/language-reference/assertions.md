---
title: "Проверочные утверждения (F#)"
description: "Дополнительные сведения о используйте выражение «assert» как средство отладки для тестирования выражений в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a><span data-ttu-id="6da25-104">Утверждения</span><span class="sxs-lookup"><span data-stu-id="6da25-104">Assertions</span></span>

<span data-ttu-id="6da25-105">`assert` Выражение — это функция отладки, можно использовать для проверки значения выражения.</span><span class="sxs-lookup"><span data-stu-id="6da25-105">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="6da25-106">При сбое в режиме отладки утверждение создает диалоговое окно системной ошибки.</span><span class="sxs-lookup"><span data-stu-id="6da25-106">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="6da25-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6da25-107">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="6da25-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6da25-108">Remarks</span></span>

<span data-ttu-id="6da25-109">`assert` Выражение имеет тип `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="6da25-109">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="6da25-110">В предыдущем синтаксисе *условие* представляет собой логическое выражение, которое необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="6da25-110">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="6da25-111">Если выражение, результатом которого является `true`, выполнение продолжается без изменений.</span><span class="sxs-lookup"><span data-stu-id="6da25-111">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="6da25-112">Если значение равно `false`, диалоговое окно ошибки системы.</span><span class="sxs-lookup"><span data-stu-id="6da25-112">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="6da25-113">Диалоговое окно ошибки имеет заголовок, содержащий строку **ложности**.</span><span class="sxs-lookup"><span data-stu-id="6da25-113">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="6da25-114">Диалоговое окно содержит трассировку стека, который указывает, где произошел сбой утверждения.</span><span class="sxs-lookup"><span data-stu-id="6da25-114">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="6da25-115">Проверка утверждений действует только при компиляции в режиме отладки; то есть если константа `DEBUG` определен.</span><span class="sxs-lookup"><span data-stu-id="6da25-115">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="6da25-116">В системе проекта, по умолчанию `DEBUG` констант определена в конфигурации отладки, но не в конфигурации выпуска.</span><span class="sxs-lookup"><span data-stu-id="6da25-116">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="6da25-117">Сбой проверочного утверждения нельзя перехватить с помощью обработки исключений в языке F #.</span><span class="sxs-lookup"><span data-stu-id="6da25-117">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="6da25-118">`assert` Функции разрешается в <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6da25-118">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="6da25-119">Пример</span><span class="sxs-lookup"><span data-stu-id="6da25-119">Example</span></span>

<span data-ttu-id="6da25-120">В следующем примере кода показано использование `assert` выражение.</span><span class="sxs-lookup"><span data-stu-id="6da25-120">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="6da25-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6da25-121">See Also</span></span>

[<span data-ttu-id="6da25-122">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6da25-122">F# Language Reference</span></span>](index.md)
