---
title: "Общие сведения о константах (Visual Basic) | Документы Microsoft"
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
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
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
ms.openlocfilehash: 2df21b9e3e814c654b355472aa645481060c6f68
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="02b63-102">Общие сведения о константах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02b63-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="02b63-103">Константа представляет собой значимое имя, вместо числа или строки, которые не изменяются.</span><span class="sxs-lookup"><span data-stu-id="02b63-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="02b63-104">Константы хранят значения, которые, как и предполагает название, остаются неизменными во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="02b63-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="02b63-105">Можно значительно повысить читаемость кода и упростить поддержку, применяя константы.</span><span class="sxs-lookup"><span data-stu-id="02b63-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="02b63-106">Их использование в коде, который содержит значения, или это зависит от числа, которые трудно запомнить или осмыслить.</span><span class="sxs-lookup"><span data-stu-id="02b63-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="02b63-107">Создание и использование констант</span><span class="sxs-lookup"><span data-stu-id="02b63-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="02b63-108">содержит ряд предопределенных констант, в основном используемые для печати и отображения.</span><span class="sxs-lookup"><span data-stu-id="02b63-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="02b63-109">Можно также создать собственные константы с `Const` инструкция, использующая те же правила, что для создания имени переменной.</span><span class="sxs-lookup"><span data-stu-id="02b63-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="02b63-110">Если `Option Strict` — `On`, необходимо явно объявлять тип константы.</span><span class="sxs-lookup"><span data-stu-id="02b63-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="02b63-111">Константа область, которая представляет собой набор весь код, на него можно ссылаться без указания полного имени, является таким же, как и для переменной, объявленной в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="02b63-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="02b63-112">Чтобы создать константу, которая существует в пределах определенной процедуры, объявите ее в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="02b63-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="02b63-113">Чтобы создать константу, доступную в рамках всего приложения, объявите его с помощью `Public` ключевое слово в раздел объявлений класса.</span><span class="sxs-lookup"><span data-stu-id="02b63-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02b63-114">Несмотря на то, что константы напоминают переменные, нельзя изменять их и присваивать новые значения для них, как к переменным.</span><span class="sxs-lookup"><span data-stu-id="02b63-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="02b63-115">Константы, которые можно использовать в коде можно определить с помощью объектной модели элементов управления или компонентов, работы с или они могут быть определяемой пользователем (то есть, созданные вами).</span><span class="sxs-lookup"><span data-stu-id="02b63-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="02b63-116">Константы времени компиляции и во время выполнения</span><span class="sxs-lookup"><span data-stu-id="02b63-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="02b63-117">Константа времени компиляции вычисляется во время компиляции кода, а константа времени выполнения может быть вычислена только во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="02b63-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="02b63-118">Константа времени компиляции будет иметь то же значение при каждом выполнении приложения, а константа времени выполнения может меняться при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="02b63-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="02b63-119">Константы времени компиляции необходимы для случаев, таких как границы массива, условные выражения или инициализаторы.</span><span class="sxs-lookup"><span data-stu-id="02b63-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02b63-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="02b63-120">In This Section</span></span>  
  
|<span data-ttu-id="02b63-121">Определение</span><span class="sxs-lookup"><span data-stu-id="02b63-121">Definition</span></span>|<span data-ttu-id="02b63-122">Термин</span><span class="sxs-lookup"><span data-stu-id="02b63-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="02b63-123">Практическое руководство. Объявление константы</span><span class="sxs-lookup"><span data-stu-id="02b63-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="02b63-124">Объясняется, как использовать `Const` инструкцию, чтобы объявить константу и задать его значение, объявив константу, присваивайте ей понятное имя, значение.</span><span class="sxs-lookup"><span data-stu-id="02b63-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="02b63-125">Константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="02b63-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="02b63-126">Описывает, как создавать собственные константы, включая сведения о видимости и как избежать циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="02b63-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="02b63-127">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="02b63-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="02b63-128">Содержит сведения о том, как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инициализации констант компилятором при `Option Explicit` отключена.</span><span class="sxs-lookup"><span data-stu-id="02b63-128">Provides information on how the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="02b63-129">Практическое руководство. Группирование значений связанных констант</span><span class="sxs-lookup"><span data-stu-id="02b63-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="02b63-130">Демонстрирует группировку постоянные значения, которые связаны.</span><span class="sxs-lookup"><span data-stu-id="02b63-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="02b63-131">Ссылки</span><span class="sxs-lookup"><span data-stu-id="02b63-131">Reference</span></span>  
  
|<span data-ttu-id="02b63-132">Определение</span><span class="sxs-lookup"><span data-stu-id="02b63-132">Definition</span></span>|<span data-ttu-id="02b63-133">Термин</span><span class="sxs-lookup"><span data-stu-id="02b63-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="02b63-134">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="02b63-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="02b63-135">Список предопределенных констант в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="02b63-135">Lists the constants predefined by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>|  
|[<span data-ttu-id="02b63-136">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="02b63-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="02b63-137">Описывает `Const` инструкции и его использования.</span><span class="sxs-lookup"><span data-stu-id="02b63-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="02b63-138">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="02b63-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="02b63-139">Описывает `Option Strict` инструкции и его использования.</span><span class="sxs-lookup"><span data-stu-id="02b63-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02b63-140">См. также</span><span class="sxs-lookup"><span data-stu-id="02b63-140">See Also</span></span>  
 <span data-ttu-id="02b63-141">[Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="02b63-141">[Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="02b63-142"> [Практическое руководство: инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="02b63-142"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
