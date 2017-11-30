---
title: "Производные математические функции (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5816fa4c8c384eca116fa1512950a3588c6e3392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="79348-102">Производные математические функции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79348-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="79348-103">В следующей таблице показаны невстроенный математические функции, которые могут быть получены из встраиваемых математических функций объекта <xref:System.Math?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="79348-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="79348-104">Доступ к встраиваемым математическим функциям, добавив `Imports System.Math` в файл или проект.</span><span class="sxs-lookup"><span data-stu-id="79348-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="79348-105">Функция</span><span class="sxs-lookup"><span data-stu-id="79348-105">Function</span></span>|<span data-ttu-id="79348-106">Производные функции</span><span class="sxs-lookup"><span data-stu-id="79348-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="79348-107">Секанс (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="79348-107">Secant (Sec(x))</span></span>|<span data-ttu-id="79348-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="79348-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="79348-109">Косеканс (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="79348-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="79348-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="79348-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="79348-111">Котангенс (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="79348-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="79348-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="79348-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="79348-113">Арксинус (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="79348-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="79348-114">ATAN (x / Sqrt (-x * x + 1))</span><span class="sxs-lookup"><span data-stu-id="79348-114">Atan(x / Sqrt(-x * x + 1))</span></span>|  
|<span data-ttu-id="79348-115">Арккосинус (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="79348-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="79348-116">ATAN (-x и Sqrt (-x * x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="79348-116">Atan(-x / Sqrt(-x * x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="79348-117">Арксеканс (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="79348-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="79348-118">2 * Atan(1) — Atan(Sign(x) и Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="79348-118">2 * Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="79348-119">Обратный косеканс (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="79348-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="79348-120">ATAN(Sign(x) / Sqrt (x * x – 1))</span><span class="sxs-lookup"><span data-stu-id="79348-120">Atan(Sign(x) / Sqrt(x * x – 1))</span></span>|  
|<span data-ttu-id="79348-121">Обратный котангенс (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="79348-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="79348-122">2 * Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="79348-122">2 * Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="79348-123">Гиперболический синус (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="79348-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="79348-124">(Exp(x) — Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="79348-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="79348-125">Гиперболический косинус (COSH(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="79348-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="79348-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="79348-127">Гиперболический тангенс (TANH(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="79348-128">(Exp(x) — Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="79348-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="79348-129">Гиперболический секанс (Sech(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="79348-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="79348-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="79348-131">Гиперболический косеканс (Csch(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="79348-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="79348-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="79348-133">Гиперболический котангенс (Coth(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="79348-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="79348-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="79348-135">Обратный гиперболический синус (Asinh(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="79348-136">Журнал (x + Sqrt (x * x + 1))</span><span class="sxs-lookup"><span data-stu-id="79348-136">Log(x + Sqrt(x * x + 1))</span></span>|  
|<span data-ttu-id="79348-137">Обратный гиперболический косинус (ACOSH(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="79348-138">Журнал (x + Sqrt (x * x – 1))</span><span class="sxs-lookup"><span data-stu-id="79348-138">Log(x + Sqrt(x * x – 1))</span></span>|  
|<span data-ttu-id="79348-139">Обратный гиперболический тангенс (ATANH(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="79348-140">Журнал ((1 + x) или (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="79348-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="79348-141">Обратный гиперболический секанс (AsесH(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="79348-142">Журнал ((Sqrt (-x * x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="79348-142">Log((Sqrt(-x * x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="79348-143">Обратный гиперболический косеканс (Acsch(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="79348-144">Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="79348-144">Log((Sign(x) * Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="79348-145">Обратный гиперболический котангенс (Acoth(x)))</span><span class="sxs-lookup"><span data-stu-id="79348-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="79348-146">Журнал ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="79348-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79348-147">См. также</span><span class="sxs-lookup"><span data-stu-id="79348-147">See Also</span></span>  
 [<span data-ttu-id="79348-148">Математические функции</span><span class="sxs-lookup"><span data-stu-id="79348-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
