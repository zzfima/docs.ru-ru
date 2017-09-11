---
title: "Константы и перечисления в Visual Basic"
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
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants, enumerations
- naming conventions, constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ef8ade1100bb660af4d968d4b600aba41073fc2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="7ad69-102">Константы и перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ad69-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="7ad69-103">Константы позволяют использовать наглядные имена вместо неизменяемых значений.</span><span class="sxs-lookup"><span data-stu-id="7ad69-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="7ad69-104">Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="7ad69-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="7ad69-105">С константами вы можете использовать значимые имена вместо чисел, чтобы сделать свой код более удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="7ad69-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="7ad69-106">Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.</span><span class="sxs-lookup"><span data-stu-id="7ad69-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="7ad69-107">Например, вы можете объявить перечисление для набора целочисленных констант, связанных с днями недели, а затем использовать в коде названия дней, а не числа.</span><span class="sxs-lookup"><span data-stu-id="7ad69-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ad69-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="7ad69-108">In This Section</span></span>  
  
|<span data-ttu-id="7ad69-109">Термин</span><span class="sxs-lookup"><span data-stu-id="7ad69-109">Term</span></span>|<span data-ttu-id="7ad69-110">Определение</span><span class="sxs-lookup"><span data-stu-id="7ad69-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="7ad69-111">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="7ad69-111">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)|<span data-ttu-id="7ad69-112">В статьях этого раздела описываются константы и их использование.</span><span class="sxs-lookup"><span data-stu-id="7ad69-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="7ad69-113">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="7ad69-113">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)|<span data-ttu-id="7ad69-114">В статьях этого раздела описываются перечисления и их использование.</span><span class="sxs-lookup"><span data-stu-id="7ad69-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="7ad69-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7ad69-115">Related Sections</span></span>  
  
|<span data-ttu-id="7ad69-116">Термин</span><span class="sxs-lookup"><span data-stu-id="7ad69-116">Term</span></span>|<span data-ttu-id="7ad69-117">Определение</span><span class="sxs-lookup"><span data-stu-id="7ad69-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="7ad69-118">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="7ad69-118">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="7ad69-119">Описание оператора `Const`, который используется для объявления констант.</span><span class="sxs-lookup"><span data-stu-id="7ad69-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="7ad69-120">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="7ad69-120">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)|<span data-ttu-id="7ad69-121">Описание оператора `Enum`, который используется для создания перечислений.</span><span class="sxs-lookup"><span data-stu-id="7ad69-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="7ad69-122">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="7ad69-122">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="7ad69-123">Описание оператора `Option Explicit`, который используется на уровне модулей для принудительного объявления всех переменных этого модуля в явном виде.</span><span class="sxs-lookup"><span data-stu-id="7ad69-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="7ad69-124">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="7ad69-124">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)|<span data-ttu-id="7ad69-125">Описание оператора `Option Infer`, который позволяет использовать вывод локального типа при объявлении переменных.</span><span class="sxs-lookup"><span data-stu-id="7ad69-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="7ad69-126">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="7ad69-126">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="7ad69-127">Описание оператора `Option Strict`, который ограничивает неявные преобразования типов данных, допуская только преобразование в сторону расширения, запрещает позднее связывание и неявную типизацию, которая приводит к типу `Object`.</span><span class="sxs-lookup"><span data-stu-id="7ad69-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|

