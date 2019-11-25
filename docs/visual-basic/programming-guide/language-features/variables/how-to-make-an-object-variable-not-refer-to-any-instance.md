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
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="79f10-102">Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79f10-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="79f10-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="79f10-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="79f10-104">To disassociate an object variable from any object instance</span><span class="sxs-lookup"><span data-stu-id="79f10-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="79f10-105">Set the variable to `Nothing` in an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="79f10-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="79f10-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="79f10-106">Robust Programming</span></span>  
 <span data-ttu-id="79f10-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span><span class="sxs-lookup"><span data-stu-id="79f10-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="79f10-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span><span class="sxs-lookup"><span data-stu-id="79f10-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="79f10-109">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="79f10-109">.NET Framework Security</span></span>  
 <span data-ttu-id="79f10-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span><span class="sxs-lookup"><span data-stu-id="79f10-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="79f10-111">This reduces the chance of malicious code gaining access to the data.</span><span class="sxs-lookup"><span data-stu-id="79f10-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f10-112">См. также</span><span class="sxs-lookup"><span data-stu-id="79f10-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="79f10-113">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="79f10-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="79f10-114">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="79f10-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="79f10-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="79f10-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="79f10-116">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="79f10-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
