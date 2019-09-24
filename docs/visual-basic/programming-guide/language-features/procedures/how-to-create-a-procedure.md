---
title: Практическое руководство. Создание процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216719"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="27645-102">Практическое руководство. Создание процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27645-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="27645-103">Процедура заключается в заключении между операторами начального объявления (`Sub` или `Function`) и завершающим оператором объявления`End Sub` ( `End Function`или).</span><span class="sxs-lookup"><span data-stu-id="27645-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="27645-104">Весь код процедуры находится между этими операторами.</span><span class="sxs-lookup"><span data-stu-id="27645-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="27645-105">Процедура не может содержать другую процедуру, поэтому ее начальные и конечные операторы должны находиться за пределами любой другой процедуры.</span><span class="sxs-lookup"><span data-stu-id="27645-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="27645-106">Если у вас есть код, выполняющий одну и ту же задачу в разных местах, можно написать задачу один раз как процедуру, а затем вызвать ее из различных мест в коде.</span><span class="sxs-lookup"><span data-stu-id="27645-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="27645-107">Создание процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="27645-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="27645-108">За пределами любой другой процедуры `Sub` используйте оператор, за которым `End Sub` следует оператор.</span><span class="sxs-lookup"><span data-stu-id="27645-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="27645-109">`Sub` В инструкции `Sub` используйте ключевое слово с именем процедуры, а затем список параметров в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="27645-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="27645-110">Поместите операторы кода процедуры между `Sub` операторами и. `End Sub`</span><span class="sxs-lookup"><span data-stu-id="27645-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="27645-111">Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="27645-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="27645-112">За пределами любой другой процедуры `Function` используйте оператор, за которым `End Function` следует оператор.</span><span class="sxs-lookup"><span data-stu-id="27645-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="27645-113">В инструкции используйте ключевое слово с именем процедуры, затем список параметров в круглых скобках, а затем `As` предложение, указывающее тип данных возвращаемого значения. `Function` `Function`</span><span class="sxs-lookup"><span data-stu-id="27645-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="27645-114">Поместите операторы кода процедуры между `Function` операторами и. `End Function`</span><span class="sxs-lookup"><span data-stu-id="27645-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="27645-115">`Return` Используйте оператор, чтобы вернуть значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="27645-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="27645-116">Подключение новой процедуры к старым и повторяющимся блокам кода</span><span class="sxs-lookup"><span data-stu-id="27645-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="27645-117">Убедитесь, что вы определили новую процедуру в том месте, где старый код имеет к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="27645-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="27645-118">В старом и повторяющемся блоке кода замените инструкции, выполняющие повторяющуюся задачу, на одну инструкцию, которая вызывает `Sub` процедуру `Function` или.</span><span class="sxs-lookup"><span data-stu-id="27645-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="27645-119">Если процедура `Function` возвращает значение, убедитесь, что вызывающая инструкция выполняет действие с возвращаемым значением, например, сохраняя его в переменной, или, в противном случае, значение будет потеряно.</span><span class="sxs-lookup"><span data-stu-id="27645-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="27645-120">Пример</span><span class="sxs-lookup"><span data-stu-id="27645-120">Example</span></span>

 <span data-ttu-id="27645-121">Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон:</span><span class="sxs-lookup"><span data-stu-id="27645-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="27645-122">См. также</span><span class="sxs-lookup"><span data-stu-id="27645-122">See also</span></span>

- [<span data-ttu-id="27645-123">Процедуры</span><span class="sxs-lookup"><span data-stu-id="27645-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="27645-124">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="27645-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="27645-125">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="27645-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="27645-126">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="27645-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="27645-127">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="27645-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="27645-128">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="27645-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="27645-129">Рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="27645-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="27645-130">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="27645-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="27645-131">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="27645-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- <span data-ttu-id="27645-132">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27645-132">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md)</span></span>
