---
title: Числовые операторы и операторы сравнения
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a1ce13225d72b4286982434d52998a1913814abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352185"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="12011-102">Числовые операторы и операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="12011-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="12011-103">Арифметические операторы и операторы сравнения работают в среде (CLR) соответствующим образом, за исключением следующих моментов.</span><span class="sxs-lookup"><span data-stu-id="12011-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="12011-104">SQL не поддерживает оператор modulus для чисел с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="12011-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="12011-105">SQL не поддерживает непроверяемые арифметические операции.</span><span class="sxs-lookup"><span data-stu-id="12011-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="12011-106">Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="12011-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="12011-107">Поддерживаемые операторы</span><span class="sxs-lookup"><span data-stu-id="12011-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="12011-108"> поддерживает следующие операторы.</span><span class="sxs-lookup"><span data-stu-id="12011-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="12011-109">Основные арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="12011-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="12011-110">`-` (вычитание)</span><span class="sxs-lookup"><span data-stu-id="12011-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="12011-111">Оператор целочисленного деления Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="12011-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="12011-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="12011-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="12011-113">`-` (унарное отрицание)</span><span class="sxs-lookup"><span data-stu-id="12011-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="12011-114">Основные операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="12011-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="12011-115">Visual Basic `=` и C# `==`</span><span class="sxs-lookup"><span data-stu-id="12011-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="12011-116">Visual Basic `<>` и C# `!=`</span><span class="sxs-lookup"><span data-stu-id="12011-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="12011-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="12011-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="12011-118">См. также</span><span class="sxs-lookup"><span data-stu-id="12011-118">See Also</span></span>  
 [<span data-ttu-id="12011-119">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="12011-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="12011-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="12011-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="12011-121">Операторы</span><span class="sxs-lookup"><span data-stu-id="12011-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
