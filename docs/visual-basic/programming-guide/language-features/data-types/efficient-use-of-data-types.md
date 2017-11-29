---
title: "Эффективное использование типов данных (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e13a1d61aacb06eb336c39aab969847127dfc67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="e367c-102">Эффективное использование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e367c-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="e367c-103">Необъявленные переменные и переменные, объявленные типами данных назначенных `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="e367c-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="e367c-104">Это упрощает написание программ, но может замедлять их выполняются медленнее.</span><span class="sxs-lookup"><span data-stu-id="e367c-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="e367c-105">Строгая типизация</span><span class="sxs-lookup"><span data-stu-id="e367c-105">Strong Typing</span></span>  
 <span data-ttu-id="e367c-106">Задание типов данных для всех переменных называется *строгую типизацию*.</span><span class="sxs-lookup"><span data-stu-id="e367c-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="e367c-107">Использование строгой типизации имеет несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="e367c-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="e367c-108">Она включает поддержку IntelliSense для переменных.</span><span class="sxs-lookup"><span data-stu-id="e367c-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="e367c-109">Это позволяет видеть свойства и другие члены, вводимые в коде.</span><span class="sxs-lookup"><span data-stu-id="e367c-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="e367c-110">Она использует преимущества проверки типа компилятора.</span><span class="sxs-lookup"><span data-stu-id="e367c-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="e367c-111">Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение.</span><span class="sxs-lookup"><span data-stu-id="e367c-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="e367c-112">Он также обнаруживаются вызовы методов для объектов, которые не поддерживают.</span><span class="sxs-lookup"><span data-stu-id="e367c-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="e367c-113">Это приводит к более быстрое выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="e367c-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="e367c-114">Наиболее эффективные типы данных</span><span class="sxs-lookup"><span data-stu-id="e367c-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="e367c-115">Для переменных, которые никогда не содержат дроби целочисленные типы данных более эффективны, чем Нецелочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="e367c-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="e367c-116">В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], `Integer` и `UInteger` являются наиболее эффективный числовых типов.</span><span class="sxs-lookup"><span data-stu-id="e367c-116">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="e367c-117">Для дробных чисел `Double` является наиболее эффективный тип данных, поскольку процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью.</span><span class="sxs-lookup"><span data-stu-id="e367c-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="e367c-118">Тем не менее операции с `Double` не выполняются так же быстро, как и для целочисленных типов, таких как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e367c-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="e367c-119">Указание типа данных</span><span class="sxs-lookup"><span data-stu-id="e367c-119">Specifying Data Type</span></span>  
 <span data-ttu-id="e367c-120">Используйте [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной определенного типа.</span><span class="sxs-lookup"><span data-stu-id="e367c-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="e367c-121">Одновременно можно указать уровень доступа с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово как Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e367c-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="e367c-122">Преобразование символов</span><span class="sxs-lookup"><span data-stu-id="e367c-122">Character Conversion</span></span>  
 <span data-ttu-id="e367c-123">`AscW` И `ChrW` функции выполняются в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="e367c-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="e367c-124">Их следует использовать `Asc` и `Chr`, который необходимо преобразовать в Юникод и из него.</span><span class="sxs-lookup"><span data-stu-id="e367c-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e367c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e367c-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="e367c-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="e367c-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e367c-127">Числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="e367c-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="e367c-128">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="e367c-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="e367c-129">Использование технологии IntelliSense</span><span class="sxs-lookup"><span data-stu-id="e367c-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
