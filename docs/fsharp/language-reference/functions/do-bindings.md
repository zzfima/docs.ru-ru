---
title: "Привязки do (F#)"
description: "Узнайте, как выполнить привязку F # используется для выполнения кода без определения функции или значения."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings"></a><span data-ttu-id="e7266-104">Привязки do</span><span class="sxs-lookup"><span data-stu-id="e7266-104">do Bindings</span></span>

<span data-ttu-id="e7266-105">Объект `do` привязка используется для выполнения кода без определения функции или значения.</span><span class="sxs-lookup"><span data-stu-id="e7266-105">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="e7266-106">Кроме того, привязки "Выполнить" можно использовать в классах см [ `do` привязок в классах](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="e7266-106">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="e7266-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7266-107">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="e7266-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7266-108">Remarks</span></span>
<span data-ttu-id="e7266-109">Используйте `do` привязки, если требуется выполнить код независимо от определения функции или значения.</span><span class="sxs-lookup"><span data-stu-id="e7266-109">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="e7266-110">Выражение в `do` привязки должен возвращать `unit`.</span><span class="sxs-lookup"><span data-stu-id="e7266-110">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="e7266-111">Код верхнего уровня `do` привязки выполняется при инициализации модуля.</span><span class="sxs-lookup"><span data-stu-id="e7266-111">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="e7266-112">Ключевое слово `do` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e7266-112">The keyword `do` is optional.</span></span>

<span data-ttu-id="e7266-113">Атрибуты могут быть применены к верхнего уровня `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="e7266-113">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="e7266-114">Например, если программа использует COM-взаимодействия, может потребоваться применить `STAThread` атрибута в программу.</span><span class="sxs-lookup"><span data-stu-id="e7266-114">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="e7266-115">Это можно сделать с помощью атрибута `do` привязки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e7266-115">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="e7266-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e7266-116">See Also</span></span>
[<span data-ttu-id="e7266-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="e7266-117">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="e7266-118">Функции</span><span class="sxs-lookup"><span data-stu-id="e7266-118">Functions</span></span>](index.md)

