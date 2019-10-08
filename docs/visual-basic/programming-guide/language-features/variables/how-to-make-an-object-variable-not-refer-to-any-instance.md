---
title: Практическое руководство. Сделать объектную переменную нессылающейся на какой-либо экземпляр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004916"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="17c99-102">Практическое руководство. Сделать объектную переменную нессылающейся на какой-либо экземпляр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17c99-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="17c99-103">Можно разорвать связь объектной переменной с любым экземпляром объекта, задав для него значение [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="17c99-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="17c99-104">Отмена связывания объектной переменной с любым экземпляром объекта</span><span class="sxs-lookup"><span data-stu-id="17c99-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="17c99-105">Присвойте переменной значение `Nothing` в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="17c99-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="17c99-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="17c99-106">Robust Programming</span></span>  
 <span data-ttu-id="17c99-107">Если код пытается получить доступ к члену объектной переменной, для которой задано значение `Nothing`, возникает <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="17c99-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="17c99-108">Если для переменной объекта присвоить значение `Nothing` часто или если переменная не инициализирована, рекомендуется заключить доступ к членам в блок `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="17c99-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="17c99-109">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="17c99-109">.NET Framework Security</span></span>  
 <span data-ttu-id="17c99-110">При использовании объектной переменной для объектов, содержащих конфиденциальные или конфиденциальные данные, можно присвоить переменной значение `Nothing`, если вы активно не работаете с одним из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="17c99-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="17c99-111">Это снижает вероятность того, что вредоносный код получает доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="17c99-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c99-112">См. также</span><span class="sxs-lookup"><span data-stu-id="17c99-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="17c99-113">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="17c99-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="17c99-114">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="17c99-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="17c99-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="17c99-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="17c99-116">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="17c99-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
