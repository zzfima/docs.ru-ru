---
title: Практическое руководство. Объявление структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 6128addd60609bfc88a1409648fb320bc7089974
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650031"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="0a003-102">Практическое руководство. Объявление структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a003-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="0a003-103">Объявление структуры с начинается [оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), и завершается оператором `End` `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="0a003-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End` `Structure` statement.</span></span> <span data-ttu-id="0a003-104">Между этими двумя операторами необходимо объявить по крайней мере один *элемент*.</span><span class="sxs-lookup"><span data-stu-id="0a003-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="0a003-105">Элементы могут иметь любой тип данных, но по крайней мере один должен быть не общей переменной или непользовательским событий.</span><span class="sxs-lookup"><span data-stu-id="0a003-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="0a003-106">Не удалось инициализировать любого из элементов структуры в объявлении структуры.</span><span class="sxs-lookup"><span data-stu-id="0a003-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="0a003-107">При объявлении переменной с типом структуры, можно присвоить значения элементы путем доступа к ним через переменную.</span><span class="sxs-lookup"><span data-stu-id="0a003-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="0a003-108">Описание различий между структур и классов см. в разделе [структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="0a003-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="0a003-109">Для простоты примера рассмотрим ситуацию, место для отслеживания имя, телефон и заработной платы сотрудника.</span><span class="sxs-lookup"><span data-stu-id="0a003-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="0a003-110">Структура позволяет сделать это в одной переменной.</span><span class="sxs-lookup"><span data-stu-id="0a003-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="0a003-111">Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="0a003-111">To declare a structure</span></span>  
  
1.  <span data-ttu-id="0a003-112">Создайте начальный и конечный инструкции для структуры.</span><span class="sxs-lookup"><span data-stu-id="0a003-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="0a003-113">Можно указать уровень доступа для структуры с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, или можно оставить значение по умолчанию `Public`.</span><span class="sxs-lookup"><span data-stu-id="0a003-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  <span data-ttu-id="0a003-114">Добавьте элементы в тело структуры.</span><span class="sxs-lookup"><span data-stu-id="0a003-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="0a003-115">Структуры должны иметь хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="0a003-115">A structure must have at least one element.</span></span> <span data-ttu-id="0a003-116">Необходимо объявить каждый элемент и указать уровень доступа для него.</span><span class="sxs-lookup"><span data-stu-id="0a003-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="0a003-117">Если вы используете [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без любых ключевых слов, доступность по умолчанию `Public`.</span><span class="sxs-lookup"><span data-stu-id="0a003-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="0a003-118">`salary` Поле в предыдущем примере является `Private`, это означает, что он недоступным за пределами структуры даже из содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="0a003-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="0a003-119">Тем не менее `giveRaise` процедура `Public`, поэтому он может быть вызвана за пределами структуры.</span><span class="sxs-lookup"><span data-stu-id="0a003-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="0a003-120">Аналогичным образом, чтобы увеличить `salaryReviewTime` событие вне структуры.</span><span class="sxs-lookup"><span data-stu-id="0a003-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="0a003-121">В дополнение к переменным `Sub` процедуры, а также события можно также определить константы, `Function` процедуры и свойства в структуре.</span><span class="sxs-lookup"><span data-stu-id="0a003-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="0a003-122">Можно назначить только одно свойство как *свойство по умолчанию*, если оно может принимать хотя бы один аргумент.</span><span class="sxs-lookup"><span data-stu-id="0a003-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="0a003-123">Можно обработать событие с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="0a003-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="0a003-124">Дополнительные сведения см. в разделе [как: объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="0a003-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a003-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0a003-125">See Also</span></span>  
 [<span data-ttu-id="0a003-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0a003-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="0a003-127">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="0a003-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="0a003-128">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="0a003-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="0a003-129">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="0a003-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="0a003-130">Структуры</span><span class="sxs-lookup"><span data-stu-id="0a003-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="0a003-131">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="0a003-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="0a003-132">Переменные структуры</span><span class="sxs-lookup"><span data-stu-id="0a003-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [<span data-ttu-id="0a003-133">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="0a003-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="0a003-134">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="0a003-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="0a003-135">Тип данных, определенный пользователем</span><span class="sxs-lookup"><span data-stu-id="0a003-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
