---
title: Практическое руководство. Определение различных версий процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: fc7a8e18394b904f0c22a80f71dee091d4f786ab
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324036"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="2a3e5-102">Практическое руководство. Определение различных версий процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a3e5-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="2a3e5-103">Можно определить процедуру в нескольких версиях, *перегрузка* его с помощью тем же именем, но другим списком параметров для каждой версии.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="2a3e5-104">Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры без необходимости различать их по имени.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="2a3e5-105">Дополнительные сведения см. в разделе [Procedure Overloading](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="2a3e5-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="2a3e5-106">Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="2a3e5-106">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="2a3e5-107">Запись `Sub` или `Function` оператор объявления для каждой версии процедуры, необходимо определить.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="2a3e5-108">Используйте то же имя процедуры в каждом объявлении.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-108">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="2a3e5-109">Перед `Sub` или `Function` ключевое слово в каждом объявлении [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="2a3e5-110">Можно опустить `Overloads` в объявлениях, но если оно включено в одном из объявлений, необходимо включить его в каждое объявление.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="2a3e5-111">После каждого оператора объявления писать код процедуры для обработки определенного случая, где вызывающий код предоставляет аргументы, соответствующие этой версии списка параметров.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="2a3e5-112">У вас нет для тестирования для каких параметров поставляет вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="2a3e5-113">Visual Basic передает управление соответствующей версии процедуры.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="2a3e5-114">Завершайте каждую процедуру с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a3e5-115">Пример</span><span class="sxs-lookup"><span data-stu-id="2a3e5-115">Example</span></span>  
 <span data-ttu-id="2a3e5-116">В следующем примере определяется `Sub` процедуры для публикации транзакций с сальдо клиента.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="2a3e5-117">Она использует `Overloads` ключевое слово для определения двух версий процедуры, принимающую клиента по имени, а другая по номеру счета.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="2a3e5-118">Вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем использовать тот же вызывающий оператор в любом случае.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="2a3e5-119">Сведения о том, как вызывать эти версии `post` процедуры, см. в разделе [как: Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="2a3e5-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a3e5-120">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2a3e5-120">Compiling the Code</span></span>  
 <span data-ttu-id="2a3e5-121">Убедитесь, что каждый перегруженные версии имеет то же имя процедуры, но другим списком параметров.</span><span class="sxs-lookup"><span data-stu-id="2a3e5-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3e5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2a3e5-122">See also</span></span>

- [<span data-ttu-id="2a3e5-123">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2a3e5-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2a3e5-124">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="2a3e5-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2a3e5-125">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="2a3e5-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="2a3e5-126">Практическое руководство. Перегрузка процедуры, которая принимает необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="2a3e5-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="2a3e5-127">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="2a3e5-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="2a3e5-128">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="2a3e5-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="2a3e5-129">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="2a3e5-129">Overload Resolution</span></span>](./overload-resolution.md)
