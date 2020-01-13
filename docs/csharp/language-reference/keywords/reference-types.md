---
title: Ссылочные типы. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 16e7cdc624979f9a35e287ea5274bd9398c83132
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715166"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="fc37e-102">Ссылочные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fc37e-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="fc37e-103">В C# существуют две разновидности типов: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="fc37e-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="fc37e-104">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="fc37e-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="fc37e-105">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="fc37e-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="fc37e-106">Каждая переменная типа значения имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую (за исключением переменных параметров in, ref и out; см. описание модификатора параметров [in](in-parameter-modifier.md), [ref](ref.md) и [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="fc37e-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="fc37e-107">Для объявления ссылочных типов используются следующие ключевые слова:</span><span class="sxs-lookup"><span data-stu-id="fc37e-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="fc37e-108">class</span><span class="sxs-lookup"><span data-stu-id="fc37e-108">class</span></span>](class.md)

- [<span data-ttu-id="fc37e-109">interface</span><span class="sxs-lookup"><span data-stu-id="fc37e-109">interface</span></span>](interface.md)

- [<span data-ttu-id="fc37e-110">delegate</span><span class="sxs-lookup"><span data-stu-id="fc37e-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="fc37e-111">В C# также предусмотрены следующие встроенные ссылочные типы:</span><span class="sxs-lookup"><span data-stu-id="fc37e-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="fc37e-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="fc37e-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="fc37e-113">object</span><span class="sxs-lookup"><span data-stu-id="fc37e-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="fc37e-114">string</span><span class="sxs-lookup"><span data-stu-id="fc37e-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="fc37e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fc37e-115">See also</span></span>

- [<span data-ttu-id="fc37e-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fc37e-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fc37e-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fc37e-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fc37e-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="fc37e-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fc37e-119">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="fc37e-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="fc37e-120">Типы значений</span><span class="sxs-lookup"><span data-stu-id="fc37e-120">Value types</span></span>](value-types.md)
