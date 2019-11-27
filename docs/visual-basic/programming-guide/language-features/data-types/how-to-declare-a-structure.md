---
title: Практическое руководство. Объявление структуры
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 41d2d03064dea703909218de56feb863526c220b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349999"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="ab721-102">Практическое руководство. Объявление структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab721-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="ab721-103">Объявление структуры начинается с [оператора Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)и завершается с помощью оператора `End Structure`.</span><span class="sxs-lookup"><span data-stu-id="ab721-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="ab721-104">Между этими двумя операторами необходимо объявить хотя бы один *элемент*.</span><span class="sxs-lookup"><span data-stu-id="ab721-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="ab721-105">Элементы могут иметь любой тип данных, но хотя бы один из них должен быть либо необщей переменной, либо нестандартным, ненастраиваемым событием.</span><span class="sxs-lookup"><span data-stu-id="ab721-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="ab721-106">Нельзя инициализировать какие либо элементы структуры в объявлении структуры.</span><span class="sxs-lookup"><span data-stu-id="ab721-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="ab721-107">При объявлении переменной, имеющей тип структуры, необходимо назначить значения элементам, обращаясь к ним через переменную.</span><span class="sxs-lookup"><span data-stu-id="ab721-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="ab721-108">Обсуждение различий между структурами и классами см. в разделе [структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="ab721-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="ab721-109">В демонстрационных целях рассмотрим ситуацию, когда необходимо отследить имя сотрудника, телефонное расширение и заработную плату.</span><span class="sxs-lookup"><span data-stu-id="ab721-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="ab721-110">Структура позволяет сделать это в одной переменной.</span><span class="sxs-lookup"><span data-stu-id="ab721-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="ab721-111">Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="ab721-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="ab721-112">Создайте начальную и конечную инструкции для структуры.</span><span class="sxs-lookup"><span data-stu-id="ab721-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="ab721-113">Уровень доступа структуры можно указать с помощью ключевого слова [Public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)или [Private](../../../../visual-basic/language-reference/modifiers/private.md) . также можно разрешить `Public`по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab721-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="ab721-114">Добавьте элементы в текст структуры.</span><span class="sxs-lookup"><span data-stu-id="ab721-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="ab721-115">Структура должна содержать по крайней мере один элемент.</span><span class="sxs-lookup"><span data-stu-id="ab721-115">A structure must have at least one element.</span></span> <span data-ttu-id="ab721-116">Необходимо объявить каждый элемент и указать для него уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="ab721-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="ab721-117">Если вы используете [инструкцию Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) без ключевых слов, для специальных возможностей по умолчанию используется значение `Public`.</span><span class="sxs-lookup"><span data-stu-id="ab721-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
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
  
     <span data-ttu-id="ab721-118">Поле `salary` в предыдущем примере имеет `Private`, что означает, что оно недоступно за пределами структуры, даже из содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="ab721-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="ab721-119">Однако процедура `giveRaise` `Public`, поэтому ее можно вызывать вне структуры.</span><span class="sxs-lookup"><span data-stu-id="ab721-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="ab721-120">Аналогичным образом можно вызвать событие `salaryReviewTime` за пределами структуры.</span><span class="sxs-lookup"><span data-stu-id="ab721-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="ab721-121">В дополнение к переменным, `Sub` процедурам и событиям можно также определить константы, `Function` процедуры и свойства в структуре.</span><span class="sxs-lookup"><span data-stu-id="ab721-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="ab721-122">Можно назначить не более одного свойства в качестве *свойства по умолчанию*при условии, что оно принимает по крайней мере один аргумент.</span><span class="sxs-lookup"><span data-stu-id="ab721-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="ab721-123">Можно выполнить обработку события с помощью [общей](../../../../visual-basic/language-reference/modifiers/shared.md) процедуры`Sub`.</span><span class="sxs-lookup"><span data-stu-id="ab721-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="ab721-124">Дополнительные сведения см. в разделе [инструкции. объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="ab721-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab721-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ab721-125">See also</span></span>

- [<span data-ttu-id="ab721-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="ab721-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="ab721-127">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="ab721-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="ab721-128">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="ab721-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="ab721-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="ab721-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="ab721-130">Структуры</span><span class="sxs-lookup"><span data-stu-id="ab721-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="ab721-131">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="ab721-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="ab721-132">Переменные структуры</span><span class="sxs-lookup"><span data-stu-id="ab721-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="ab721-133">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="ab721-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="ab721-134">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="ab721-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="ab721-135">Тип данных, определенный пользователем</span><span class="sxs-lookup"><span data-stu-id="ab721-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
