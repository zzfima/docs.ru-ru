---
title: Привязки do
description: Узнайте, как F# «do» привязка используется для выполнения кода без определения функции или значения.
ms.date: 05/16/2016
ms.openlocfilehash: d29f8557fda06097d2e85748ab6286f0415730b3
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614523"
---
# <a name="do-bindings"></a><span data-ttu-id="c4502-103">Привязки do</span><span class="sxs-lookup"><span data-stu-id="c4502-103">do Bindings</span></span>

<span data-ttu-id="c4502-104">Привязка `do` используется для выполнения кода без определения функции или значения.</span><span class="sxs-lookup"><span data-stu-id="c4502-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="c4502-105">Кроме того, привязки `do` можно использовать в классах см [привязки `do` в классах](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="c4502-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="c4502-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4502-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="c4502-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4502-107">Remarks</span></span>

<span data-ttu-id="c4502-108">Используйте привязки `do`, если требуется выполнить код независимо от определения функции или значения.</span><span class="sxs-lookup"><span data-stu-id="c4502-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="c4502-109">Выражение в привязке `do` должно возвращать значение `unit`.</span><span class="sxs-lookup"><span data-stu-id="c4502-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="c4502-110">Код в привязке `do` верхнего уровня выполняется при инициализации модуля.</span><span class="sxs-lookup"><span data-stu-id="c4502-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="c4502-111">Ключевое слово `do` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c4502-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="c4502-112">Атрибуты могут быть применены к привязке `do` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c4502-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="c4502-113">Например, если программа использует COM-взаимодействия, может потребоваться применить в программе атрибут `STAThread`.</span><span class="sxs-lookup"><span data-stu-id="c4502-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="c4502-114">Это можно сделать с помощью атрибута привязки `do`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c4502-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="c4502-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c4502-115">See also</span></span>

- [<span data-ttu-id="c4502-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="c4502-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="c4502-117">Функции</span><span class="sxs-lookup"><span data-stu-id="c4502-117">Functions</span></span>](index.md)