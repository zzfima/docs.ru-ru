---
title: Практическое руководство. Объявление структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343562"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="3b630-102">Практическое руководство. Объявление структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b630-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="3b630-103">Начать объявление структуры [оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), и завершается с `End Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3b630-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="3b630-104">Между этими двумя операторами должен быть объявлен по крайней мере *элемент*.</span><span class="sxs-lookup"><span data-stu-id="3b630-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="3b630-105">Элементы могут быть любого типа данных, но по крайней мере один должен быть не являющаяся общей переменная или непользовательским событий.</span><span class="sxs-lookup"><span data-stu-id="3b630-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="3b630-106">Вы не можете инициализировать любого из элементов структуры в объявлении структуры.</span><span class="sxs-lookup"><span data-stu-id="3b630-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="3b630-107">Если объявить переменную типа структуры, присваиваются значения в элементы, доступ к ним через переменную.</span><span class="sxs-lookup"><span data-stu-id="3b630-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="3b630-108">Описание различий между структуры и классы, см. в разделе [структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="3b630-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="3b630-109">Для демонстрационных целей рассмотрим ситуацию, место для отслеживания имя сотрудника, телефон и заработной платы.</span><span class="sxs-lookup"><span data-stu-id="3b630-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="3b630-110">Структура позволяет сделать это в одной переменной.</span><span class="sxs-lookup"><span data-stu-id="3b630-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="3b630-111">Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="3b630-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="3b630-112">Создайте начальный и конечный инструкции для структуры.</span><span class="sxs-lookup"><span data-stu-id="3b630-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="3b630-113">Можно указать уровень доступа структуры с помощью [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово, или можно разрешить его по умолчанию `Public`.</span><span class="sxs-lookup"><span data-stu-id="3b630-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="3b630-114">Добавьте элементы в тексте структуры.</span><span class="sxs-lookup"><span data-stu-id="3b630-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="3b630-115">Структуры должны иметь хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="3b630-115">A structure must have at least one element.</span></span> <span data-ttu-id="3b630-116">Необходимо объявить каждый элемент и указать уровень доступа для него.</span><span class="sxs-lookup"><span data-stu-id="3b630-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="3b630-117">Если вы используете [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без любые ключевые слова, доступность по умолчанию `Public`.</span><span class="sxs-lookup"><span data-stu-id="3b630-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
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
  
     <span data-ttu-id="3b630-118">`salary` Поле в предыдущем примере является `Private`, который означает, что он недоступен вне структуры, даже от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="3b630-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="3b630-119">Тем не менее `giveRaise` процедура `Public`, поэтому он может вызываться из вне структуры.</span><span class="sxs-lookup"><span data-stu-id="3b630-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="3b630-120">Аналогичным образом, вы можете отправить `salaryReviewTime` событие вне структуры.</span><span class="sxs-lookup"><span data-stu-id="3b630-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="3b630-121">Кроме переменных `Sub` процедуры и события, можно также определить константы, `Function` процедуры и свойства в структуре.</span><span class="sxs-lookup"><span data-stu-id="3b630-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="3b630-122">Можно указать не более одного свойства как *свойство по умолчанию*, предоставляющего по крайней мере один аргумент.</span><span class="sxs-lookup"><span data-stu-id="3b630-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="3b630-123">Можно обработать событие с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3b630-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="3b630-124">Дополнительные сведения см. в разделе [Как Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="3b630-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b630-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3b630-125">See also</span></span>

- [<span data-ttu-id="3b630-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="3b630-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="3b630-127">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="3b630-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="3b630-128">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="3b630-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="3b630-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="3b630-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="3b630-130">Структуры</span><span class="sxs-lookup"><span data-stu-id="3b630-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3b630-131">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="3b630-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="3b630-132">Переменные структуры</span><span class="sxs-lookup"><span data-stu-id="3b630-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="3b630-133">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="3b630-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="3b630-134">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="3b630-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="3b630-135">Тип данных, определенный пользователем</span><span class="sxs-lookup"><span data-stu-id="3b630-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
