---
title: Различия между параметрами и аргументами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a69b956c7cffcc2a26916d6fc92f23dd4e2322d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838980"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="fd7cf-102">Различия между параметрами и аргументами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd7cf-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="fd7cf-103">В большинстве случаев процедура должна иметь некоторые сведения об условиях ее возникновения, в которых она была вызвана.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="fd7cf-104">Процедура, выполняющая повторяющихся или общих задач использует различные сведения для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="fd7cf-105">Эта информация состоит из переменных, констант и выражений, которые передаются в процедуру при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="fd7cf-106">Для передачи этих сведений к процедуре, определяет *параметр*, а вызывающий код передает *аргумент* в этот параметр.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="fd7cf-107">Можно представить параметр как парковкой пробел и аргумент как автомобиль.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="fd7cf-108">Так же, как различные автомобили могут парковаться в пространстве парковкой в разное время, вызывающий код может передать другой аргумент к тому же параметру, каждый раз, чтобы он вызывает процедуру.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="fd7cf-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd7cf-109">Parameters</span></span>  
 <span data-ttu-id="fd7cf-110">Объект *параметр* представляет значение, которое процедура ожидает передачи при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="fd7cf-111">Объявление процедуры определяет его параметры.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="fd7cf-112">При определении `Function` или `Sub` процедуры, указывать *список параметров* в скобках сразу после имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="fd7cf-113">Для каждого параметра укажите имя, тип данных и механизм передачи ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="fd7cf-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="fd7cf-114">Можно также указать, что параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="fd7cf-115">Это означает, что вызывающий код не имеет значение передается для него.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="fd7cf-116">Имя каждого параметра служит в качестве *локальной переменной* в процедуре.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="fd7cf-117">Имя параметра используется так же, как любая другая переменная.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="fd7cf-118">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fd7cf-118">Arguments</span></span>  
 <span data-ttu-id="fd7cf-119">*Аргумент* представляет значение, которое передается параметр процедуры при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="fd7cf-120">Вызывающий код предоставляет аргументы при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="fd7cf-121">При вызове `Function` или `Sub` процедуры, включают *список аргументов* в скобках сразу после имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="fd7cf-122">Каждый аргумент соответствует параметру в той же позиции в списке.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="fd7cf-123">В отличие от определения параметров аргументы не имеют имен.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="fd7cf-124">Каждый аргумент является выражение, которое может содержать ноль или дополнительные переменные, константы и литералы.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="fd7cf-125">Тип данных вычисленного выражения должен соответствовать типу данных, определенному для соответствующего параметра, и в любом случае должно быть преобразуемым к типу параметра.</span><span class="sxs-lookup"><span data-stu-id="fd7cf-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7cf-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fd7cf-126">See also</span></span>

- [<span data-ttu-id="fd7cf-127">Процедуры</span><span class="sxs-lookup"><span data-stu-id="fd7cf-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fd7cf-128">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="fd7cf-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="fd7cf-129">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="fd7cf-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="fd7cf-130">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="fd7cf-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fd7cf-131">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="fd7cf-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="fd7cf-132">Практическое руководство. Определение параметра для процедуры</span><span class="sxs-lookup"><span data-stu-id="fd7cf-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="fd7cf-133">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="fd7cf-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="fd7cf-134">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="fd7cf-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="fd7cf-135">Рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="fd7cf-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="fd7cf-136">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="fd7cf-136">Procedure Overloading</span></span>](./procedure-overloading.md)
