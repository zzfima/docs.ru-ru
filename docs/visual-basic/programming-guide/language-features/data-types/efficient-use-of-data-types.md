---
title: Эффективное использование типов данных
ms.date: 07/20/2015
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
ms.openlocfilehash: 621dec7537e9c993024e271b96ab8706baf89885
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350107"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="c6a88-102">Эффективное использование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6a88-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="c6a88-103">Необъявленные переменные и переменные, объявленные без типа данных, назначаются `Object` типу данных.</span><span class="sxs-lookup"><span data-stu-id="c6a88-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="c6a88-104">Это упрощает написание программ, но может привести к более медленному их выполнению.</span><span class="sxs-lookup"><span data-stu-id="c6a88-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="c6a88-105">Строгая типизация</span><span class="sxs-lookup"><span data-stu-id="c6a88-105">Strong Typing</span></span>
 <span data-ttu-id="c6a88-106">Указание типов данных для всех переменных называется *строгой типизацией*.</span><span class="sxs-lookup"><span data-stu-id="c6a88-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="c6a88-107">Использование строгой типизации имеет несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="c6a88-107">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="c6a88-108">Он обеспечивает поддержку IntelliSense для переменных.</span><span class="sxs-lookup"><span data-stu-id="c6a88-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="c6a88-109">Это позволяет просматривать их свойства и другие члены по мере ввода кода.</span><span class="sxs-lookup"><span data-stu-id="c6a88-109">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="c6a88-110">Он использует преимущества проверки типов компилятора.</span><span class="sxs-lookup"><span data-stu-id="c6a88-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="c6a88-111">Это перехватывает инструкции, которые могут завершиться ошибкой во время выполнения из-за таких ошибок, как переполнение.</span><span class="sxs-lookup"><span data-stu-id="c6a88-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="c6a88-112">Он также перехватывает вызовы методов для объектов, которые их не поддерживают.</span><span class="sxs-lookup"><span data-stu-id="c6a88-112">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="c6a88-113">Это приводит к ускорению выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="c6a88-113">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="c6a88-114">Наиболее эффективные типы данных</span><span class="sxs-lookup"><span data-stu-id="c6a88-114">Most Efficient Data Types</span></span>
 <span data-ttu-id="c6a88-115">Для переменных, которые никогда не содержат дробей, целочисленные типы данных более эффективны, чем Нецелочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="c6a88-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="c6a88-116">В Visual Basic `Integer` и `UInteger` являются наиболее эффективными числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="c6a88-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="c6a88-117">Для дробных чисел `Double` является наиболее эффективным типом данных, так как процессоры на текущих платформах выполняют операции с плавающей запятой с двойной точностью.</span><span class="sxs-lookup"><span data-stu-id="c6a88-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="c6a88-118">Однако операции с `Double` не так быстро, как с целочисленными типами, такими как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c6a88-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="c6a88-119">Указание типа данных</span><span class="sxs-lookup"><span data-stu-id="c6a88-119">Specifying Data Type</span></span>
 <span data-ttu-id="c6a88-120">Используйте [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной определенного типа.</span><span class="sxs-lookup"><span data-stu-id="c6a88-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="c6a88-121">Уровень доступа можно указать одновременно с помощью ключевого слова [Public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)или [Private](../../../../visual-basic/language-reference/modifiers/private.md) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c6a88-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="c6a88-122">Преобразование символов</span><span class="sxs-lookup"><span data-stu-id="c6a88-122">Character Conversion</span></span>
 <span data-ttu-id="c6a88-123">Функции `AscW` и `ChrW` работают в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="c6a88-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="c6a88-124">Их следует использовать в предпочтениях `Asc` и `Chr`, которые должны преобразовываться в Юникод и из него.</span><span class="sxs-lookup"><span data-stu-id="c6a88-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6a88-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c6a88-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="c6a88-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c6a88-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="c6a88-127">Числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="c6a88-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="c6a88-128">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="c6a88-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="c6a88-129">Использование технологии IntelliSense</span><span class="sxs-lookup"><span data-stu-id="c6a88-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
