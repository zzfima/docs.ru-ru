---
title: "Пользовательские константы (Visual Basic) | Документы Microsoft"
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
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
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
ms.openlocfilehash: b1ab1501309823b1565d5198fff25edf2927a2ce
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="4c9b3-102">Константы, определенные пользователем (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c9b3-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="4c9b3-103">Константа представляет собой значимое имя, вместо числа или строки, которые не изменяются.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="4c9b3-104">Константы хранят значения, которые, как и предполагает название, остаются неизменными во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="4c9b3-105">Можно использовать константы, определенные элементами управления или компонентов, с которыми работают, или создавать собственные.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="4c9b3-106">Созданные пользователем константы называются *пользовательские*.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="4c9b3-107">Объявление константы с `Const` инструкция, использующая те же правила, что для создания имени переменной.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="4c9b3-108">Если `Option Strict` — `On`, необходимо явно объявлять тип константы.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="4c9b3-109">Использование оператора Const</span><span class="sxs-lookup"><span data-stu-id="4c9b3-109">Const Statement Usage</span></span>  
 <span data-ttu-id="4c9b3-110">A `Const` оператор может представляет числовые и временные показатели:</span><span class="sxs-lookup"><span data-stu-id="4c9b3-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 <span data-ttu-id="4c9b3-111">[!code-vb[VbEnumsTask&#10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c9b3-111">[!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span></span>  
  
 <span data-ttu-id="4c9b3-112">Также можно определить `String` константы:</span><span class="sxs-lookup"><span data-stu-id="4c9b3-112">It also can define `String` constants:</span></span>  
  
 <span data-ttu-id="4c9b3-113">[!code-vb[VbEnumsTask&#13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c9b3-113">[!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span></span>  
  
 <span data-ttu-id="4c9b3-114">Выражение справа от знака равенства ( `=` ) часто является числом или буквенной строкой, но она может быть выражением, результатом вычисления в строку или число (хотя это выражение не может содержать вызовы функций).</span><span class="sxs-lookup"><span data-stu-id="4c9b3-114">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="4c9b3-115">Вы даже можете определить константы в терминах ранее определенных констант:</span><span class="sxs-lookup"><span data-stu-id="4c9b3-115">You can even define constants in terms of previously defined constants:</span></span>  
  
 <span data-ttu-id="4c9b3-116">[!code-vb[VbEnumsTask&#15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c9b3-116">[!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span></span>  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="4c9b3-117">Область действия константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="4c9b3-117">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="4c9b3-118">A `Const` областью инструкции является таким же, как и для переменной, объявленной в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-118">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="4c9b3-119">Можно указать область в любой из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="4c9b3-119">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="4c9b3-120">Чтобы создать константу, которая существует только в пределах процедуры, объявите ее в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-120">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="4c9b3-121">Чтобы создать константу, доступную всем процедурам класса, но не для кода за пределами модуля, следует объявите ее в разделе объявлений класса.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-121">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="4c9b3-122">Чтобы создать константу, которая доступна всем членам сборки, но не внешним клиентам сборки, объявите его с помощью `Friend` ключевое слово в раздел объявлений класса.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-122">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="4c9b3-123">Чтобы создать константу, доступную в рамках всего приложения, следует объявить ее с помощью `Public` ключевых слов в объявлениях раздел класса.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-123">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="4c9b3-124">Дополнительные сведения см. в разделе [как: объявления констант](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="4c9b3-124">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="4c9b3-125">Чтобы избежать циклических ссылок</span><span class="sxs-lookup"><span data-stu-id="4c9b3-125">Avoiding Circular References</span></span>  
 <span data-ttu-id="4c9b3-126">Поскольку константы могут определяться другими константами, существует возможность случайного создания *цикла*, или циклической ссылки между двумя или несколькими константами.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-126">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="4c9b3-127">Цикл возникает, когда два или несколько открытых констант, каждый из которых определяется в терминах других, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4c9b3-127">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 <span data-ttu-id="4c9b3-128">[!code-vb[VbEnumsTask №&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c9b3-128">[!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span></span>  
<span data-ttu-id="4c9b3-129">[!code-vb[VbEnumsTask&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c9b3-129">[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span></span>  
  
 <span data-ttu-id="4c9b3-130">При возникновении цикла, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] приводит к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="4c9b3-130">If a cycle occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9b3-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4c9b3-131">See Also</span></span>  
 <span data-ttu-id="4c9b3-132">[Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-132">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="4c9b3-133"> [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-133"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="4c9b3-134"> [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-134"> [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span></span>  
<span data-ttu-id="4c9b3-135"> [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-135"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span></span>  
<span data-ttu-id="4c9b3-136"> [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-136"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="4c9b3-137"> [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-137"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="4c9b3-138"> [Практическое руководство: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-138"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="4c9b3-139"> [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="4c9b3-139"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="4c9b3-140"> [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4c9b3-140"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
