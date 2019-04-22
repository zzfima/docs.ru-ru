---
title: Производные математические функции (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836588"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="cf6e8-102">Производные математические функции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="cf6e8-103">В следующей таблице показаны невстроенной математические функции, которые могут быть получены из встроенных математических функций из <xref:System.Math?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="cf6e8-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="cf6e8-104">Доступ к встроенных математических функций, добавив `Imports System.Math` в проект или файл.</span><span class="sxs-lookup"><span data-stu-id="cf6e8-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="cf6e8-105">Функция</span><span class="sxs-lookup"><span data-stu-id="cf6e8-105">Function</span></span>|<span data-ttu-id="cf6e8-106">Производные функции</span><span class="sxs-lookup"><span data-stu-id="cf6e8-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="cf6e8-107">Секанс (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-107">Secant (Sec(x))</span></span>|<span data-ttu-id="cf6e8-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="cf6e8-109">Косеканс (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="cf6e8-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="cf6e8-111">Котангенс (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="cf6e8-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="cf6e8-113">Арксинус (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="cf6e8-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="cf6e8-115">Арккосинус (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="cf6e8-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="cf6e8-117">Арксеканс (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="cf6e8-118">2 \* Atan(1) — Atan(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="cf6e8-119">Обратный косеканс (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="cf6e8-120">ATAN(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="cf6e8-121">Обратный котангенс (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="cf6e8-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="cf6e8-123">Гиперболический синус (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="cf6e8-124">(Exp(x) — Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="cf6e8-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="cf6e8-125">Гиперболический косинус (COSH(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="cf6e8-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="cf6e8-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="cf6e8-127">Гиперболический тангенс (TANH(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="cf6e8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="cf6e8-129">Гиперболический секанс (Sech(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="cf6e8-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="cf6e8-131">Гиперболический косеканс (Csch(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="cf6e8-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="cf6e8-133">Гиперболический котангенс (Coth(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="cf6e8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="cf6e8-135">Обратный гиперболический синус (Asinh(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="cf6e8-136">Log (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="cf6e8-137">Обратный гиперболический косинус (ACOSH(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="cf6e8-138">Log (x + Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="cf6e8-139">Обратный гиперболический тангенс (ATANH(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="cf6e8-140">Журнал ((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="cf6e8-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="cf6e8-141">Обратный гиперболический секанс (AsесH(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="cf6e8-142">Log ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="cf6e8-143">Обратный гиперболический косеканс (Acsch(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="cf6e8-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="cf6e8-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="cf6e8-145">Обратный гиперболический котангенс (Acoth(x)))</span><span class="sxs-lookup"><span data-stu-id="cf6e8-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="cf6e8-146">Журнал ((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="cf6e8-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf6e8-147">См. также</span><span class="sxs-lookup"><span data-stu-id="cf6e8-147">See also</span></span>

- [<span data-ttu-id="cf6e8-148">Математические функции</span><span class="sxs-lookup"><span data-stu-id="cf6e8-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
