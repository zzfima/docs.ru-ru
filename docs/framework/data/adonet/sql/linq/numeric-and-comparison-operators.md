---
title: "Числовые операторы и операторы сравнения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f77cb612468b401f6aa526e46cc7481d0b47d385
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="28141-102">Числовые операторы и операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="28141-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="28141-103">Арифметические операторы и операторы сравнения работают в среде (CLR) соответствующим образом, за исключением следующих моментов.</span><span class="sxs-lookup"><span data-stu-id="28141-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="28141-104">SQL не поддерживает оператор modulus для чисел с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="28141-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="28141-105">SQL не поддерживает непроверяемые арифметические операции.</span><span class="sxs-lookup"><span data-stu-id="28141-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="28141-106">Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="28141-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="28141-107">Поддерживаемые операторы</span><span class="sxs-lookup"><span data-stu-id="28141-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="28141-108"> поддерживает следующие операторы.</span><span class="sxs-lookup"><span data-stu-id="28141-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="28141-109">Основные арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="28141-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="28141-110">`-` (вычитание)</span><span class="sxs-lookup"><span data-stu-id="28141-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="28141-111">Оператор целочисленного деления Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="28141-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="28141-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="28141-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="28141-113">`-` (унарное отрицание)</span><span class="sxs-lookup"><span data-stu-id="28141-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="28141-114">Основные операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="28141-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="28141-115">Visual Basic `=` и C# `==`</span><span class="sxs-lookup"><span data-stu-id="28141-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="28141-116">Visual Basic `<>` и C# `!=`</span><span class="sxs-lookup"><span data-stu-id="28141-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="28141-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="28141-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="28141-118">См. также</span><span class="sxs-lookup"><span data-stu-id="28141-118">See Also</span></span>  
 [<span data-ttu-id="28141-119">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="28141-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="28141-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="28141-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="28141-121">Операторы</span><span class="sxs-lookup"><span data-stu-id="28141-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
