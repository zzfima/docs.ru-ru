---
title: Практическое руководство. Создание процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344913"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="778c6-102">Практическое руководство. Создание процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="778c6-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="778c6-103">Вы заключаете процедуру между оператором начального объявления (`Sub` или `Function`) и завершающим оператором объявления (`End Sub` или `End Function`).</span><span class="sxs-lookup"><span data-stu-id="778c6-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="778c6-104">Весь код процедуры находится между этими операторами.</span><span class="sxs-lookup"><span data-stu-id="778c6-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="778c6-105">Процедура не может содержать другую процедуру, поэтому ее начальные и конечные операторы должны находиться за пределами любой другой процедуры.</span><span class="sxs-lookup"><span data-stu-id="778c6-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="778c6-106">Если у вас есть код, выполняющий одну и ту же задачу в разных местах, можно написать задачу один раз как процедуру, а затем вызвать ее из различных мест в коде.</span><span class="sxs-lookup"><span data-stu-id="778c6-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="778c6-107">Создание процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="778c6-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="778c6-108">За пределами любой другой процедуры используйте оператор `Sub`, за которым следует инструкция `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="778c6-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="778c6-109">В операторе `Sub` используйте ключевое слово `Sub` с именем процедуры, а затем список параметров в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="778c6-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="778c6-110">Поместите операторы кода процедуры между операторами `Sub` и `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="778c6-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="778c6-111">Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="778c6-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="778c6-112">За пределами любой другой процедуры используйте оператор `Function`, за которым следует инструкция `End Function`.</span><span class="sxs-lookup"><span data-stu-id="778c6-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="778c6-113">В операторе `Function` используйте ключевое слово `Function` с именем процедуры, затем список параметров в круглых скобках, а затем предложение `As`, указывающее тип данных возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="778c6-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="778c6-114">Поместите операторы кода процедуры между операторами `Function` и `End Function`.</span><span class="sxs-lookup"><span data-stu-id="778c6-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="778c6-115">Используйте оператор `Return`, чтобы вернуть значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="778c6-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="778c6-116">Подключение новой процедуры к старым и повторяющимся блокам кода</span><span class="sxs-lookup"><span data-stu-id="778c6-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="778c6-117">Убедитесь, что вы определили новую процедуру в том месте, где старый код имеет к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="778c6-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="778c6-118">В старом и повторяющемся блоке кода замените инструкции, выполняющие повторяющуюся задачу, одной инструкцией, которая вызывает `Sub` или `Function` процедуру.</span><span class="sxs-lookup"><span data-stu-id="778c6-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="778c6-119">Если процедура является `Function`, возвращающей значение, убедитесь, что вызывающая инструкция выполняет действие с возвращаемым значением, например, сохранив его в переменной, или в противном случае значение будет потеряно.</span><span class="sxs-lookup"><span data-stu-id="778c6-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="778c6-120">Пример</span><span class="sxs-lookup"><span data-stu-id="778c6-120">Example</span></span>

 <span data-ttu-id="778c6-121">Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон:</span><span class="sxs-lookup"><span data-stu-id="778c6-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="778c6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="778c6-122">See also</span></span>

- [<span data-ttu-id="778c6-123">Процедуры</span><span class="sxs-lookup"><span data-stu-id="778c6-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="778c6-124">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="778c6-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="778c6-125">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="778c6-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="778c6-126">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="778c6-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="778c6-127">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="778c6-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="778c6-128">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="778c6-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="778c6-129">Рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="778c6-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="778c6-130">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="778c6-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="778c6-131">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="778c6-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- <span data-ttu-id="778c6-132">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="778c6-132">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md)</span></span>
