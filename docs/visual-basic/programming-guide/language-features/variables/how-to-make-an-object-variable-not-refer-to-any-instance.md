---
title: Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 8f85ba0adea522851e45b20ef5024491874c9a29
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744025"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="5b549-102">Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b549-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="5b549-103">При установке для него можно разорвать связь объектной переменной с любым экземпляром объекта [ничего не](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="5b549-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="5b549-104">Чтобы разорвать связь с любым экземпляром объекта переменной объекта</span><span class="sxs-lookup"><span data-stu-id="5b549-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="5b549-105">Присвойте переменной `Nothing` в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="5b549-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="5b549-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="5b549-106">Robust Programming</span></span>  
 <span data-ttu-id="5b549-107">Если код пытается получить доступ к члену переменной объекта, которое было задано для `Nothing`, <xref:System.NullReferenceException> происходит.</span><span class="sxs-lookup"><span data-stu-id="5b549-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="5b549-108">Если задано значение переменной объекта `Nothing` часто, или если это возможно, переменная не инициализирована, рекомендуется заключать доступе к членам в `Try...Catch...Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="5b549-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5b549-109">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5b549-109">.NET Framework Security</span></span>  
 <span data-ttu-id="5b549-110">Если вы используете переменную объекта для объектов, содержащих конфиденциальные данные, можно присвоить переменной `Nothing` Если вы не работаете активно с одного из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="5b549-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="5b549-111">Это снижает вероятность вредоносного кода, доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="5b549-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b549-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5b549-112">See Also</span></span>  
 <xref:System.NullReferenceException>  
 [<span data-ttu-id="5b549-113">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="5b549-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="5b549-114">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="5b549-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="5b549-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="5b549-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="5b549-116">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="5b549-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="5b549-117">Разрешение вопросов, связанных с исключениями: System.NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="5b549-117">Troubleshooting Exceptions: System.NullReferenceException</span></span>](https://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
