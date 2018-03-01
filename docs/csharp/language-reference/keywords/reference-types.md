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
ms.openlocfilehash: c4f87363246deccf282b499aa2afee2a14d41593
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="b3c3a-102">Ссылочные типы (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b3c3a-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="b3c3a-103">В C# существуют две разновидности типов: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="b3c3a-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="b3c3a-104">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="b3c3a-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="b3c3a-105">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="b3c3a-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="b3c3a-106">Каждая переменная типа значения имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую (за исключением переменных параметров ref и out, см. разделы [ref](../../../csharp/language-reference/keywords/ref.md) и [Модификатор параметров out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="b3c3a-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of ref and out parameter variables, see [ref](../../../csharp/language-reference/keywords/ref.md) and [out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span></span>  
  
 <span data-ttu-id="b3c3a-107">Для объявления ссылочных типов используются следующие ключевые слова:</span><span class="sxs-lookup"><span data-stu-id="b3c3a-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="b3c3a-108">class</span><span class="sxs-lookup"><span data-stu-id="b3c3a-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="b3c3a-109">interface</span><span class="sxs-lookup"><span data-stu-id="b3c3a-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="b3c3a-110">delegate</span><span class="sxs-lookup"><span data-stu-id="b3c3a-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="b3c3a-111">В C# также предусмотрены следующие встроенные ссылочные типы:</span><span class="sxs-lookup"><span data-stu-id="b3c3a-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="b3c3a-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="b3c3a-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="b3c3a-113">object</span><span class="sxs-lookup"><span data-stu-id="b3c3a-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="b3c3a-114">string</span><span class="sxs-lookup"><span data-stu-id="b3c3a-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3c3a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b3c3a-115">See Also</span></span>  
 [<span data-ttu-id="b3c3a-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b3c3a-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b3c3a-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b3c3a-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b3c3a-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b3c3a-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b3c3a-119">Типы</span><span class="sxs-lookup"><span data-stu-id="b3c3a-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="b3c3a-120">Типы значений</span><span class="sxs-lookup"><span data-stu-id="b3c3a-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
