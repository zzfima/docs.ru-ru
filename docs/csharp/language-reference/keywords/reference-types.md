---
title: Ссылочные типы (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: f99415fc9a2b728917cdf829ffb9e25823a824dd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43392576"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="62e57-102">Ссылочные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="62e57-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="62e57-103">В C# существуют две разновидности типов: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="62e57-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="62e57-104">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="62e57-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="62e57-105">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="62e57-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="62e57-106">Каждая переменная типа значения имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую (за исключением переменных параметров in, ref и out; см. описание модификатора параметров [in](in-parameter-modifier.md), [ref](ref.md) и [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="62e57-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="62e57-107">Для объявления ссылочных типов используются следующие ключевые слова:</span><span class="sxs-lookup"><span data-stu-id="62e57-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="62e57-108">class</span><span class="sxs-lookup"><span data-stu-id="62e57-108">class</span></span>](class.md)

- [<span data-ttu-id="62e57-109">interface</span><span class="sxs-lookup"><span data-stu-id="62e57-109">interface</span></span>](interface.md)

- [<span data-ttu-id="62e57-110">delegate</span><span class="sxs-lookup"><span data-stu-id="62e57-110">delegate</span></span>](delegate.md)

 <span data-ttu-id="62e57-111">В C# также предусмотрены следующие встроенные ссылочные типы:</span><span class="sxs-lookup"><span data-stu-id="62e57-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="62e57-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="62e57-112">dynamic</span></span>](dynamic.md)

- [<span data-ttu-id="62e57-113">object</span><span class="sxs-lookup"><span data-stu-id="62e57-113">object</span></span>](object.md)

- [<span data-ttu-id="62e57-114">string</span><span class="sxs-lookup"><span data-stu-id="62e57-114">string</span></span>](string.md)

## <a name="see-also"></a><span data-ttu-id="62e57-115">См. также</span><span class="sxs-lookup"><span data-stu-id="62e57-115">See also</span></span>

- [<span data-ttu-id="62e57-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="62e57-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="62e57-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="62e57-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="62e57-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="62e57-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="62e57-119">Типы</span><span class="sxs-lookup"><span data-stu-id="62e57-119">Types</span></span>](types.md)
- [<span data-ttu-id="62e57-120">Типы значений</span><span class="sxs-lookup"><span data-stu-id="62e57-120">Value Types</span></span>](value-types.md)