---
title: Константы и перечисления в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants [Visual Basic]
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants [Visual Basic], enumerations
- naming conventions [Visual Basic], constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
ms.openlocfilehash: dfd9330210dd748d739cd8da2985795099beacd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="fcf04-102">Константы и перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcf04-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="fcf04-103">Константы позволяют использовать наглядные имена вместо неизменяемых значений.</span><span class="sxs-lookup"><span data-stu-id="fcf04-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="fcf04-104">Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="fcf04-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="fcf04-105">С константами вы можете использовать значимые имена вместо чисел, чтобы сделать свой код более удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="fcf04-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="fcf04-106">Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.</span><span class="sxs-lookup"><span data-stu-id="fcf04-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="fcf04-107">Например, вы можете объявить перечисление для набора целочисленных констант, связанных с днями недели, а затем использовать в коде названия дней, а не числа.</span><span class="sxs-lookup"><span data-stu-id="fcf04-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcf04-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fcf04-108">In This Section</span></span>  
  
|<span data-ttu-id="fcf04-109">Термин</span><span class="sxs-lookup"><span data-stu-id="fcf04-109">Term</span></span>|<span data-ttu-id="fcf04-110">Определение</span><span class="sxs-lookup"><span data-stu-id="fcf04-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="fcf04-111">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="fcf04-111">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)|<span data-ttu-id="fcf04-112">В статьях этого раздела описываются константы и их использование.</span><span class="sxs-lookup"><span data-stu-id="fcf04-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="fcf04-113">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="fcf04-113">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)|<span data-ttu-id="fcf04-114">В статьях этого раздела описываются перечисления и их использование.</span><span class="sxs-lookup"><span data-stu-id="fcf04-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="fcf04-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fcf04-115">Related Sections</span></span>  
  
|<span data-ttu-id="fcf04-116">Термин</span><span class="sxs-lookup"><span data-stu-id="fcf04-116">Term</span></span>|<span data-ttu-id="fcf04-117">Определение</span><span class="sxs-lookup"><span data-stu-id="fcf04-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="fcf04-118">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="fcf04-118">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="fcf04-119">Описание оператора `Const`, который используется для объявления констант.</span><span class="sxs-lookup"><span data-stu-id="fcf04-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="fcf04-120">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="fcf04-120">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)|<span data-ttu-id="fcf04-121">Описание оператора `Enum`, который используется для создания перечислений.</span><span class="sxs-lookup"><span data-stu-id="fcf04-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="fcf04-122">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="fcf04-122">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="fcf04-123">Описание оператора `Option Explicit`, который используется на уровне модулей для принудительного объявления всех переменных этого модуля в явном виде.</span><span class="sxs-lookup"><span data-stu-id="fcf04-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="fcf04-124">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="fcf04-124">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)|<span data-ttu-id="fcf04-125">Описание оператора `Option Infer`, который позволяет использовать вывод локального типа при объявлении переменных.</span><span class="sxs-lookup"><span data-stu-id="fcf04-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="fcf04-126">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="fcf04-126">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="fcf04-127">Описание оператора `Option Strict`, который ограничивает неявные преобразования типов данных, допуская только преобразование в сторону расширения, запрещает позднее связывание и неявную типизацию, которая приводит к типу `Object`.</span><span class="sxs-lookup"><span data-stu-id="fcf04-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
