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
# <a name="derived-math-functions-visual-basic"></a>Производные математические функции (Visual Basic)
В следующей таблице показаны невстроенный математические функции, которые могут быть получены из встраиваемых математических функций объекта <xref:System.Math?displayProperty=nameWithType> объекта. Доступ к встраиваемым математическим функциям, добавив `Imports System.Math` в файл или проект.  
  
|Функция|Производные функции|  
|--------------|-------------------------|  
|Секанс (Sec(x))|1 / Cos(x)|  
|Косеканс (Csc(x))|1 / Sin(x)|  
|Котангенс (Ctan(x))|1 / Tan(x)|  
|Арксинус (Asin(x))|ATAN (x / Sqrt (-x * x + 1))|  
|Арккосинус (Acos(x))|ATAN (-x и Sqrt (-x * x + 1)) + 2 \* Atan(1)|  
|Арксеканс (Asec(x))|2 * Atan(1) — Atan(Sign(x) и Sqrt (x \* x – 1))|  
|Обратный косеканс (Acsc(x))|ATAN(Sign(x) / Sqrt (x * x – 1))|  
|Обратный котангенс (Acot(x))|2 * Atan(1) - Atan(x)|  
|Гиперболический синус (Sinh(x))|(Exp(x) — Exp(-x)) / 2|  
|Гиперболический косинус (COSH(x)))|(Exp(x) + Exp(-x)) / 2|  
|Гиперболический тангенс (TANH(x)))|(Exp(x) — Exp(-x)) / (Exp(x) + Exp(-x))|  
|Гиперболический секанс (Sech(x)))|2 / (Exp(x) + Exp(-x))|  
|Гиперболический косеканс (Csch(x)))|2 / (Exp(x) – Exp(-x))|  
|Гиперболический котангенс (Coth(x)))|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|Обратный гиперболический синус (Asinh(x)))|Журнал (x + Sqrt (x * x + 1))|  
|Обратный гиперболический косинус (ACOSH(x)))|Журнал (x + Sqrt (x * x – 1))|  
|Обратный гиперболический тангенс (ATANH(x)))|Журнал ((1 + x) или (1 – x)) / 2|  
|Обратный гиперболический секанс (AsесH(x)))|Журнал ((Sqrt (-x * x + 1) + 1) / x)|  
|Обратный гиперболический косеканс (Acsch(x)))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|Обратный гиперболический котангенс (Acoth(x)))|Журнал ((x + 1) / (x-1)) / 2|  
  
## <a name="see-also"></a>См. также  
 [Математические функции](../../../visual-basic/language-reference/functions/math-functions.md)
