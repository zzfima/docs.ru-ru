---
title: Привязки do (F#)
description: 'Узнайте, как выполнить привязку F # используется для выполнения кода без определения функции или значения.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings"></a><span data-ttu-id="8e91b-103">Привязки do</span><span class="sxs-lookup"><span data-stu-id="8e91b-103">do Bindings</span></span>

<span data-ttu-id="8e91b-104">Объект `do` привязка используется для выполнения кода без определения функции или значения.</span><span class="sxs-lookup"><span data-stu-id="8e91b-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="8e91b-105">Кроме того, привязки "Выполнить" можно использовать в классах см [ `do` привязок в классах](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="8e91b-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="8e91b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e91b-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="8e91b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e91b-107">Remarks</span></span>
<span data-ttu-id="8e91b-108">Используйте `do` привязки, если требуется выполнить код независимо от определения функции или значения.</span><span class="sxs-lookup"><span data-stu-id="8e91b-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="8e91b-109">Выражение в `do` привязки должен возвращать `unit`.</span><span class="sxs-lookup"><span data-stu-id="8e91b-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="8e91b-110">Код верхнего уровня `do` привязки выполняется при инициализации модуля.</span><span class="sxs-lookup"><span data-stu-id="8e91b-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="8e91b-111">Ключевое слово `do` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8e91b-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="8e91b-112">Атрибуты могут быть применены к верхнего уровня `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="8e91b-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="8e91b-113">Например, если программа использует COM-взаимодействия, может потребоваться применить `STAThread` атрибута в программу.</span><span class="sxs-lookup"><span data-stu-id="8e91b-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="8e91b-114">Это можно сделать с помощью атрибута `do` привязки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8e91b-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="8e91b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8e91b-115">See Also</span></span>
[<span data-ttu-id="8e91b-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="8e91b-116">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="8e91b-117">Функции</span><span class="sxs-lookup"><span data-stu-id="8e91b-117">Functions</span></span>](index.md)

