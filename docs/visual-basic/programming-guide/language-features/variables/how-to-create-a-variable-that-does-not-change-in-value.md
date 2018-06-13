---
title: Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651380"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="2787b-102">Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2787b-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="2787b-103">Понятие переменной, которая не изменяет его значение может показаться противоречивым.</span><span class="sxs-lookup"><span data-stu-id="2787b-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="2787b-104">Но существуют ситуации, когда константа не может быть выполнено и полезно иметь переменную с фиксированным значением.</span><span class="sxs-lookup"><span data-stu-id="2787b-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="2787b-105">В этом случае можно определить переменную-член с [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2787b-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="2787b-106">Нельзя использовать [оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) для объявления и присвоения постоянного значения в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="2787b-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="2787b-107">`Const` Инструкция не принимает тип данных, который вы хотите использовать</span><span class="sxs-lookup"><span data-stu-id="2787b-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="2787b-108">Вы не знаете значение во время компиляции</span><span class="sxs-lookup"><span data-stu-id="2787b-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="2787b-109">Не удается вычислить постоянное значение во время компиляции</span><span class="sxs-lookup"><span data-stu-id="2787b-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="2787b-110">Создание переменной, которая не изменяет значение</span><span class="sxs-lookup"><span data-stu-id="2787b-110">To create a variable that does not change in value</span></span>  
  
1.  <span data-ttu-id="2787b-111">На уровне модуля, объявите переменную-член с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)и включать [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2787b-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="2787b-112">Можно указать `ReadOnly` только на переменную-член.</span><span class="sxs-lookup"><span data-stu-id="2787b-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="2787b-113">Это означает, что необходимо определить переменную на уровне модуля, вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="2787b-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2.  <span data-ttu-id="2787b-114">Если можно вычислить значение в одной инструкции во время компиляции, используйте предложение инициализации в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2787b-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="2787b-115">Выполните [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение со знака равенства (`=`), за которым следует выражение.</span><span class="sxs-lookup"><span data-stu-id="2787b-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="2787b-116">Убедитесь, что компилятор может вычислить это выражение с постоянным значением.</span><span class="sxs-lookup"><span data-stu-id="2787b-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="2787b-117">Можно присвоить значение `ReadOnly` переменной только один раз.</span><span class="sxs-lookup"><span data-stu-id="2787b-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="2787b-118">После этого код не может изменяться его значение.</span><span class="sxs-lookup"><span data-stu-id="2787b-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="2787b-119">Если вы не знаете значение во время компиляции или не может вычислить во время компиляции в одной инструкции, вы по-прежнему можно назначить во время выполнения в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="2787b-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="2787b-120">Чтобы сделать это, необходимо объявить `ReadOnly` переменных на уровне класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="2787b-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="2787b-121">В конструкторе для этого класса или структуры вычисление фиксированное значение переменной и присвоить его переменной перед возвратом из конструктора.</span><span class="sxs-lookup"><span data-stu-id="2787b-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2787b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2787b-122">See Also</span></span>  
 [<span data-ttu-id="2787b-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="2787b-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="2787b-124">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="2787b-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
