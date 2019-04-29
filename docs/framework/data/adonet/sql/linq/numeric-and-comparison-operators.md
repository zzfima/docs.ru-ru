---
title: Числовые операторы и операторы сравнения
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: b29f78a13d6d0313e0ad29754f6d13ac08be1092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783140"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="1170e-102">Числовые операторы и операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="1170e-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="1170e-103">Арифметические операторы и операторы сравнения работают в среде (CLR) соответствующим образом, за исключением следующих моментов.</span><span class="sxs-lookup"><span data-stu-id="1170e-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="1170e-104">SQL не поддерживает оператор modulus для чисел с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="1170e-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="1170e-105">SQL не поддерживает непроверяемые арифметические операции.</span><span class="sxs-lookup"><span data-stu-id="1170e-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="1170e-106">Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1170e-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="1170e-107">Поддерживаемые операторы</span><span class="sxs-lookup"><span data-stu-id="1170e-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="1170e-108">поддерживает следующие операторы.</span><span class="sxs-lookup"><span data-stu-id="1170e-108">supports the following operators.</span></span>

- <span data-ttu-id="1170e-109">Основные арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="1170e-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="1170e-110">`-` (вычитание)</span><span class="sxs-lookup"><span data-stu-id="1170e-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="1170e-111">Оператор целочисленного деления Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="1170e-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="1170e-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="1170e-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="1170e-113">`-` (унарное отрицание)</span><span class="sxs-lookup"><span data-stu-id="1170e-113">`-` (unary negation)</span></span>

- <span data-ttu-id="1170e-114">Основные операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="1170e-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="1170e-115">Visual Basic `=` и C# `==`</span><span class="sxs-lookup"><span data-stu-id="1170e-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="1170e-116">Visual Basic `<>` и C# `!=`</span><span class="sxs-lookup"><span data-stu-id="1170e-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="1170e-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="1170e-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="1170e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1170e-118">See also</span></span>

- [<span data-ttu-id="1170e-119">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="1170e-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [<span data-ttu-id="1170e-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1170e-120">C# Operators</span></span>](../../../../../../docs/csharp/language-reference/operators/index.md)
- [<span data-ttu-id="1170e-121">Инструкции</span><span class="sxs-lookup"><span data-stu-id="1170e-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
