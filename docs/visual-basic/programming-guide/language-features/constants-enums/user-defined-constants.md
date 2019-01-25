---
title: Константы, определенные пользователем (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: dc940105bbeb5e54819b8df5d5b3c831c7a6e145
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527319"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="fac83-102">Константы, определенные пользователем (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac83-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="fac83-103">Константа — это понятное имя, заменяющее числа или строки, которые не изменяются.</span><span class="sxs-lookup"><span data-stu-id="fac83-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="fac83-104">Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="fac83-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="fac83-105">Вы можете использовать константы, определенные элементы управления или компонентов, которыми вы работаете, или создать свой собственный.</span><span class="sxs-lookup"><span data-stu-id="fac83-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="fac83-106">Константы, созданных вами самостоятельно называются *пользовательские*.</span><span class="sxs-lookup"><span data-stu-id="fac83-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="fac83-107">Объявление константы с `Const` инструкцию, используя те же правила, как для создания имени переменной.</span><span class="sxs-lookup"><span data-stu-id="fac83-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="fac83-108">Если `Option Strict` является `On`, необходимо явно объявить тип константы.</span><span class="sxs-lookup"><span data-stu-id="fac83-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="fac83-109">Использование оператора Const</span><span class="sxs-lookup"><span data-stu-id="fac83-109">Const Statement Usage</span></span>  
 <span data-ttu-id="fac83-110">Объект `Const` оператор может представляет числовые и временные показатели:</span><span class="sxs-lookup"><span data-stu-id="fac83-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 <span data-ttu-id="fac83-111">Он также может определять `String` константы:</span><span class="sxs-lookup"><span data-stu-id="fac83-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 <span data-ttu-id="fac83-112">Выражение справа от знака равенства ( `=` ) часто является числом, либо строковый литерал, но он также может быть выражением, результатом является числом или строкой (несмотря на то, что это выражение не может содержать вызовы функций).</span><span class="sxs-lookup"><span data-stu-id="fac83-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="fac83-113">Вы даже можете определять константы с точки зрения ранее определенных констант:</span><span class="sxs-lookup"><span data-stu-id="fac83-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="fac83-114">Область константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="fac83-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="fac83-115">Объект `Const` инструкции области совпадает со значением, переменной, объявленной в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="fac83-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="fac83-116">Области можно указать в любом из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="fac83-116">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="fac83-117">Чтобы создать константу, которая существует только в рамках процедуры, необходимо объявите ее в рамках этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="fac83-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="fac83-118">Чтобы создать константу, доступную для всех процедур в пределах класса, но не для кода за пределами модуля, объявите его в раздел объявлений класса.</span><span class="sxs-lookup"><span data-stu-id="fac83-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="fac83-119">Чтобы создать константу, которая доступна всем членам сборки, но не внешним клиентам сборки, объявите его с помощью `Friend` ключевое слово в раздел объявлений класса.</span><span class="sxs-lookup"><span data-stu-id="fac83-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="fac83-120">Чтобы создать константу, доступной для всего приложения, объявите его с помощью `Public` ключевое слово в объявлениях разделе класса.</span><span class="sxs-lookup"><span data-stu-id="fac83-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="fac83-121">Дополнительные сведения см. в разделе [Как Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="fac83-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="fac83-122">Избежать циклических ссылок</span><span class="sxs-lookup"><span data-stu-id="fac83-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="fac83-123">Так как константы могут быть определены с точки зрения другие константы, существует возможность случайного создания *цикл*, или циклической ссылки между двумя или более констант.</span><span class="sxs-lookup"><span data-stu-id="fac83-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="fac83-124">Цикл происходит, когда у вас есть два или более открытые константы, каждый из которых определяется в терминах другой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fac83-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 <span data-ttu-id="fac83-125">При возникновении цикла, Visual Basic создает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="fac83-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac83-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fac83-126">See also</span></span>
- [<span data-ttu-id="fac83-127">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="fac83-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="fac83-128">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="fac83-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="fac83-129">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="fac83-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="fac83-130">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="fac83-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="fac83-131">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="fac83-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="fac83-132">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="fac83-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="fac83-133">Практическое руководство. Объявления перечисления</span><span class="sxs-lookup"><span data-stu-id="fac83-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="fac83-134">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="fac83-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="fac83-135">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="fac83-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
