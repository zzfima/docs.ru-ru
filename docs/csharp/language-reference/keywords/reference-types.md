---
title: "Ссылочные типы (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e671abac6d49170ac76e4633c4f55c50dcbe01c6
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="1532d-102">Ссылочные типы (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1532d-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="1532d-103">В C# существуют две разновидности типов: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="1532d-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="1532d-104">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="1532d-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="1532d-105">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="1532d-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="1532d-106">Каждая переменная типа значения имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую (за исключением переменных параметров in, ref и out; см. описание модификатора параметров [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) и [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="1532d-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter modifier).</span></span>  
  
 <span data-ttu-id="1532d-107">Для объявления ссылочных типов используются следующие ключевые слова:</span><span class="sxs-lookup"><span data-stu-id="1532d-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="1532d-108">class</span><span class="sxs-lookup"><span data-stu-id="1532d-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="1532d-109">interface</span><span class="sxs-lookup"><span data-stu-id="1532d-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="1532d-110">delegate</span><span class="sxs-lookup"><span data-stu-id="1532d-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="1532d-111">В C# также предусмотрены следующие встроенные ссылочные типы:</span><span class="sxs-lookup"><span data-stu-id="1532d-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="1532d-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="1532d-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="1532d-113">object</span><span class="sxs-lookup"><span data-stu-id="1532d-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="1532d-114">string</span><span class="sxs-lookup"><span data-stu-id="1532d-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="1532d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1532d-115">See Also</span></span>  
 [<span data-ttu-id="1532d-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1532d-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1532d-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1532d-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1532d-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="1532d-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1532d-119">Типы</span><span class="sxs-lookup"><span data-stu-id="1532d-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="1532d-120">Типы значений</span><span class="sxs-lookup"><span data-stu-id="1532d-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
