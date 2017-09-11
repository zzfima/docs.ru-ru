---
title: "Эффективное использование типов данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ca8d5885aea12a3f1f9cb35f08bf63c1a89e7ebc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="ca06a-102">Эффективное использование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca06a-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="ca06a-103">Необъявленные переменные и переменные без типа данных назначаются `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="ca06a-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="ca06a-104">Это упрощает написание программ, но может замедлять их выполнение.</span><span class="sxs-lookup"><span data-stu-id="ca06a-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="ca06a-105">Строгая типизация</span><span class="sxs-lookup"><span data-stu-id="ca06a-105">Strong Typing</span></span>  
 <span data-ttu-id="ca06a-106">Задание типов данных для всех переменных называется *строгой типизации*.</span><span class="sxs-lookup"><span data-stu-id="ca06a-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="ca06a-107">Использование строгой типизации имеет несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="ca06a-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="ca06a-108">Он обеспечивает поддержку IntelliSense для переменных.</span><span class="sxs-lookup"><span data-stu-id="ca06a-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="ca06a-109">Это позволяет видеть их свойства и другие члены, при вводе в коде.</span><span class="sxs-lookup"><span data-stu-id="ca06a-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="ca06a-110">Он использует преимущества проверки типа компилятора.</span><span class="sxs-lookup"><span data-stu-id="ca06a-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="ca06a-111">Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение.</span><span class="sxs-lookup"><span data-stu-id="ca06a-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="ca06a-112">Обнаруживаются также вызовы методов для объектов, которые не поддерживают их.</span><span class="sxs-lookup"><span data-stu-id="ca06a-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="ca06a-113">Обеспечивается более быстрое выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="ca06a-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="ca06a-114">Наиболее эффективные типы данных</span><span class="sxs-lookup"><span data-stu-id="ca06a-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="ca06a-115">Для переменных, которые никогда не содержат дроби целочисленные типы данных более эффективны, чем Нецелочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="ca06a-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="ca06a-116">В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` и `UInteger` являются наиболее эффективными типами.</span><span class="sxs-lookup"><span data-stu-id="ca06a-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="ca06a-117">Для дробных чисел `Double` является наиболее эффективный тип данных, поскольку процессоры на современных платформах выполняют операции с плавающей запятой с двойной точностью.</span><span class="sxs-lookup"><span data-stu-id="ca06a-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="ca06a-118">Однако операции с `Double` не так же быстро, как и в случае целочисленные типы, такие как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ca06a-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="ca06a-119">Указание типа данных</span><span class="sxs-lookup"><span data-stu-id="ca06a-119">Specifying Data Type</span></span>  
 <span data-ttu-id="ca06a-120">Используйте [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной определенного типа.</span><span class="sxs-lookup"><span data-stu-id="ca06a-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="ca06a-121">Одновременно можно указать уровень доступа с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [защищенные](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ca06a-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="ca06a-122">Преобразование символов</span><span class="sxs-lookup"><span data-stu-id="ca06a-122">Character Conversion</span></span>  
 <span data-ttu-id="ca06a-123">`AscW` И `ChrW` функции выполняются в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="ca06a-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="ca06a-124">Их следует использовать `Asc` и `Chr`, которые должны преобразовывать в Юникод и из него.</span><span class="sxs-lookup"><span data-stu-id="ca06a-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca06a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ca06a-125">See Also</span></span>  
 <span data-ttu-id="ca06a-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A></span><span class="sxs-lookup"><span data-stu-id="ca06a-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></span></span>   
 <span data-ttu-id="ca06a-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="ca06a-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
 <span data-ttu-id="ca06a-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A></span><span class="sxs-lookup"><span data-stu-id="ca06a-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></span></span>   
 <span data-ttu-id="ca06a-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="ca06a-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>   
<span data-ttu-id="ca06a-130"> [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca06a-130"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="ca06a-131"> [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="ca06a-131"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="ca06a-132"> [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="ca06a-132"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="ca06a-133"> [Использование технологии IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span><span class="sxs-lookup"><span data-stu-id="ca06a-133"> [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span></span>
