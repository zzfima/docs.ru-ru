---
title: Практическое руководство. Сделать переменная объекта ссылается на любой экземпляр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 373d4ae84c44b212ad02b0b4266af75921e40423
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818694"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="4b596-102">Практическое руководство. Сделать переменная объекта ссылается на любой экземпляр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b596-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="4b596-103">При установке для него можно разорвать связь объектной переменной с любым экземпляром объекта [ничего не](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="4b596-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="4b596-104">Чтобы разорвать связь с любым экземпляром объекта переменной объекта</span><span class="sxs-lookup"><span data-stu-id="4b596-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="4b596-105">Присвойте переменной `Nothing` в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="4b596-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="4b596-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4b596-106">Robust Programming</span></span>  
 <span data-ttu-id="4b596-107">Если код пытается получить доступ к члену переменной объекта, которое было задано для `Nothing`, <xref:System.NullReferenceException> происходит.</span><span class="sxs-lookup"><span data-stu-id="4b596-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="4b596-108">Если задано значение переменной объекта `Nothing` часто, или если это возможно, переменная не инициализирована, рекомендуется заключать доступе к членам в `Try...Catch...Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="4b596-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4b596-109">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4b596-109">.NET Framework Security</span></span>  
 <span data-ttu-id="4b596-110">Если вы используете переменную объекта для объектов, содержащих конфиденциальные данные, можно присвоить переменной `Nothing` Если вы не работаете активно с одного из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="4b596-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="4b596-111">Это снижает вероятность вредоносного кода, доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="4b596-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b596-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4b596-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="4b596-113">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="4b596-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="4b596-114">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="4b596-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="4b596-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="4b596-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="4b596-116">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="4b596-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
