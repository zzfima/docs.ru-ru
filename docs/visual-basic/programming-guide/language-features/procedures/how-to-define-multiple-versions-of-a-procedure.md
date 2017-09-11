---
title: "Практическое руководство: определение различных версий процедуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f4296ba3a78316b70011bcca18f7071716f3c90d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="0bcb4-102">Практическое руководство. Определение различных версий процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bcb4-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="0bcb4-103">Можно определить процедуру в нескольких версиях с *перегрузка* его, используя то же имя, но другой список параметров для каждой версии.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="0bcb4-104">Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры, не различая их по имени.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="0bcb4-105">Дополнительные сведения см. в разделе [перегрузка процедур](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="0bcb4-106">Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="0bcb4-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="0bcb4-107">Запись `Sub` или `Function` оператор объявления для каждой версии процедуры, необходимо определить.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="0bcb4-108">Используйте то же имя процедуры в каждом объявлении.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="0bcb4-109">Перед `Sub` или `Function` ключевое слово в каждом объявлении [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="0bcb4-110">Можно опустить `Overloads` в объявлениях, но если оно включено в одном из объявлений, необходимо включить его в каждом объявлении.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="0bcb4-111">После каждого оператора объявления напишите код процедуры для обработки определенного случая, когда вызывающий код предоставляет аргументы, соответствующие этой версии списка параметров.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="0bcb4-112">Не нужно проверить для каких параметров вызывающий код имеет указанный.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-112">You do not have to test for which parameters the calling code has supplied.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0bcb4-113">передает управление соответствующей версии процедуры.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-113"> passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="0bcb4-114">Завершайте каждую процедуру с `End Sub` или `End Function` инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bcb4-115">Пример</span><span class="sxs-lookup"><span data-stu-id="0bcb4-115">Example</span></span>  
 <span data-ttu-id="0bcb4-116">В следующем примере определяется `Sub` процедура проводки транзакции по балансу клиента.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="0bcb4-117">Он использует `Overloads` ключевое слово для определения двух версий процедуры, принимающую клиента по имени, а другая — по номеру счета.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 <span data-ttu-id="0bcb4-118">[!code-vb[VbVbcnProcedures&#72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0bcb4-118">[!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="0bcb4-119">Вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем использовать тот же вызывающий оператор в обоих случаях.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-119">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="0bcb4-120">Сведения о том, как вызывать эти версии `post` процедура, в разделе [как: вызов процедуры перегруженные](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-120">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0bcb4-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0bcb4-121">Compiling the Code</span></span>  
 <span data-ttu-id="0bcb4-122">Убедитесь, что каждый перегруженные версии имеет то же имя процедуры, но с другим списком параметров.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-122">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcb4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0bcb4-123">See Also</span></span>  
 <span data-ttu-id="0bcb4-124">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="0bcb4-124">[Procedures](./index.md) </span></span>  
<span data-ttu-id="0bcb4-125"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="0bcb4-125"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="0bcb4-126"> [Рекомендации по устранению неполадок](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bcb4-126"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="0bcb4-127"> [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="0bcb4-127"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="0bcb4-128"> [Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="0bcb4-128"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="0bcb4-129"> [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0bcb4-129"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="0bcb4-130"> [Разрешение перегрузки](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="0bcb4-130"> [Overload Resolution](./overload-resolution.md)</span></span>
