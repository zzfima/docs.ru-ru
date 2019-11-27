---
title: Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352893"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="7ee4d-102">Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ee4d-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="7ee4d-103">Можно разорвать связь объектной переменной с любым экземпляром объекта, задав для него значение [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="7ee4d-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="7ee4d-104">Отмена связывания объектной переменной с любым экземпляром объекта</span><span class="sxs-lookup"><span data-stu-id="7ee4d-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="7ee4d-105">Задайте для переменной значение `Nothing` в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="7ee4d-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="7ee4d-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="7ee4d-106">Robust Programming</span></span>  
 <span data-ttu-id="7ee4d-107">Если код пытается получить доступ к члену объектной переменной, для которой задано значение `Nothing`, происходит <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="7ee4d-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="7ee4d-108">Если переменная объекта присвоена `Nothing` часто или если переменная не инициализирована, рекомендуется заключить доступ к членам в блок `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="7ee4d-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7ee4d-109">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7ee4d-109">.NET Framework Security</span></span>  
 <span data-ttu-id="7ee4d-110">При использовании объектной переменной для объектов, содержащих конфиденциальные или конфиденциальные данные, можно присвоить переменной значение `Nothing`, если вы не работаете с одним из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="7ee4d-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="7ee4d-111">Это снижает вероятность того, что вредоносный код получает доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="7ee4d-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee4d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7ee4d-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="7ee4d-113">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="7ee4d-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="7ee4d-114">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="7ee4d-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="7ee4d-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="7ee4d-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="7ee4d-116">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="7ee4d-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
