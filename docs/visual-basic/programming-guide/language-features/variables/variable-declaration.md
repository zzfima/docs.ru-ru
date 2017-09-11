---
title: "Объявление переменной в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: dac536b99eb4515c75381dc4e28720a92e1001f0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="4d9ba-102">Объявление переменной в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d9ba-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="4d9ba-103">Объявите переменную, чтобы указать ее имя и характеристики.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="4d9ba-104">Оператор объявления переменных — [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="4d9ba-105">Его местоположение и содержание определяют характеристики переменной.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="4d9ba-106">Правила именования переменных и рекомендации см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="4d9ba-107">Уровни объявления</span><span class="sxs-lookup"><span data-stu-id="4d9ba-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="4d9ba-108">Локальные и переменные-члены</span><span class="sxs-lookup"><span data-stu-id="4d9ba-108">Local and Member Variables</span></span>  
 <span data-ttu-id="4d9ba-109">Объект *локальной переменной* —, объявленная внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="4d9ba-110">Объект *переменной-члена* является членом [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] введите; он объявлен на уровне модуля, внутри класса, структуры или модуля, но не внутри любых процедур для этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-110">A *member variable* is a member of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="4d9ba-111">Экземпляров и общие переменные</span><span class="sxs-lookup"><span data-stu-id="4d9ba-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="4d9ba-112">В классе или структуре категорию переменную-член зависит от того, является ли он является общим.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="4d9ba-113">Если он был объявлен с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) это ключевое слово, *общей переменной*, и существует в единственном экземпляре, общим для всех экземпляров класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="4d9ba-114">В противном случае это *переменную экземпляра*, и отдельные ее копии создаются для каждого экземпляра класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="4d9ba-115">Каждая копия переменной экземпляра доступна только для экземпляра класса или структуры, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="4d9ba-116">Он является независимым от копия переменной экземпляра в любом экземпляре класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="4d9ba-117">Объявление типа данных</span><span class="sxs-lookup"><span data-stu-id="4d9ba-117">Declaring Data Type</span></span>  
 <span data-ttu-id="4d9ba-118">[Как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение в операторе объявления позволяет определить тип данных или тип объекта объявление переменной.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="4d9ba-119">Можно указать любой из следующих типов переменных:</span><span class="sxs-lookup"><span data-stu-id="4d9ba-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="4d9ba-120">Простой тип данных, таких как `Boolean`, `Long`, или`Decimal`</span><span class="sxs-lookup"><span data-stu-id="4d9ba-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="4d9ba-121">Составные типы данных, такие как массив или структура.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="4d9ba-122">Тип объекта или класс, определенный в приложении или в другом приложении</span><span class="sxs-lookup"><span data-stu-id="4d9ba-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="4d9ba-123">Объект [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] класса, такие как <xref:System.Windows.Forms.Label>или <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="4d9ba-123">A [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="4d9ba-124">Тип интерфейса, такие как <xref:System.IComparable>или <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="4d9ba-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="4d9ba-125">Можно объявить несколько переменных в одном операторе без повторения типа данных.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="4d9ba-126">В следующих операторах переменные `i`, `j`, и `k` объявлен как тип `Integer`, `l` и `m` как `Long`, и `x` и `y` как `Single`:</span><span class="sxs-lookup"><span data-stu-id="4d9ba-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="4d9ba-127">Дополнительные сведения о типах данных см. в разделе [типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="4d9ba-128">Дополнительные сведения об объектах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [программирование с использованием компонентов](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="4d9ba-129">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="4d9ba-129">Local Type Inference</span></span>  
 <span data-ttu-id="4d9ba-130">*Вывод типа* используется для определения типов данных локальных переменных, объявленных без `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="4d9ba-131">Компилятор выводит тип переменной из типа выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="4d9ba-132">Это позволяет объявлять переменные без явного указания типа.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="4d9ba-133">В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="4d9ba-134">[!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d9ba-134">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span></span>  
  
 <span data-ttu-id="4d9ba-135">Если вы хотите использовать вывод локального типа `Option Infer` должно быть присвоено `On`.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-135">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="4d9ba-136">Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Option Infer оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="4d9ba-137">Характеристики объявленных переменных</span><span class="sxs-lookup"><span data-stu-id="4d9ba-137">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="4d9ba-138">*Время существования* переменной — это период времени, во время которого он доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-138">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="4d9ba-139">В общем случае переменная существует, пока продолжает существовать элемент, объявляющий ее (например, процедура или класс).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-139">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="4d9ba-140">Если переменная не требуется прекратиться после окончания времени существования содержащего ее элемента, не требуется никаких действий в объявлении.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-140">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="4d9ba-141">Если переменная должна существовать дольше, чем содержащий ее элемент, можно включить `Static` или `Shared` ключевое слово в его `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-141">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="4d9ba-142">Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-142">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="4d9ba-143">*Область* переменной — это набор всех элементов кода, на него можно ссылаться без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-143">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="4d9ba-144">Область переменной определяется, где она объявлена.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-144">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="4d9ba-145">Код, расположенный в заданном регионе можно использовать переменные, определенные в этой области, без уточнения их имена.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-145">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="4d9ba-146">Дополнительные сведения см. в разделе [область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-146">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="4d9ba-147">Переменная *уровень доступа* является область кода, имеющего разрешение на доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-147">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="4d9ba-148">Это определяется модификатор доступа (такие как [открытый](../../../../visual-basic/language-reference/modifiers/public.md) или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md)), используемого в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4d9ba-148">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="4d9ba-149">Дополнительные сведения см. в разделе [уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ba-149">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9ba-150">См. также</span><span class="sxs-lookup"><span data-stu-id="4d9ba-150">See Also</span></span>  
 <span data-ttu-id="4d9ba-151">[Практическое руководство: Создание новой переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-151">[How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span></span>  
<span data-ttu-id="4d9ba-152"> [Практическое руководство: перемещение данных в действие и из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-152"> [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
<span data-ttu-id="4d9ba-153"> [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-153"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="4d9ba-154"> [Защищенные](../../../../visual-basic/language-reference/modifiers/protected.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-154"> [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) </span></span>  
<span data-ttu-id="4d9ba-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span></span>  
<span data-ttu-id="4d9ba-156"> [Статические](../../../../visual-basic/language-reference/modifiers/static.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-156"> [Static](../../../../visual-basic/language-reference/modifiers/static.md) </span></span>  
<span data-ttu-id="4d9ba-157"> [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-157"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="4d9ba-158"> [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="4d9ba-158"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="4d9ba-159"> [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4d9ba-159"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>
