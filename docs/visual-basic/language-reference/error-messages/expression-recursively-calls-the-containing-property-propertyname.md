---
title: "Выражение рекурсивно вызывает содержащее свойство &quot;&lt;propertyname&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
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
ms.openlocfilehash: c7168ab2a2ec5eb0c0d423120b67c10b117c14b2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="fabd4-102">Выражение рекурсивно вызывает содержащее свойство "&lt;propertyname&gt;"</span><span class="sxs-lookup"><span data-stu-id="fabd4-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="fabd4-103">Оператор в `Set` процедура определения свойства сохраняет значение в имени свойства.</span><span class="sxs-lookup"><span data-stu-id="fabd4-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="fabd4-104">Рекомендуемый подход для хранения значения свойства является определение `Private` переменных в контейнере свойства и использование его в `Get` и `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="fabd4-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="fabd4-105">`Set` Процедура затем будет хранить входящее значение в этой `Private` переменной.</span><span class="sxs-lookup"><span data-stu-id="fabd4-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="fabd4-106">`Get` Процедура действует как `Function` процедуру, чтобы назначить значение имени свойства и вернуть управление путем добавления `End Get` инструкции.</span><span class="sxs-lookup"><span data-stu-id="fabd4-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="fabd4-107">Однако рекомендуется включать `Private` в качестве значения переменной [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fabd4-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="fabd4-108">`Set` Процедура действует как `Sub` процедуры, которая не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="fabd4-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="fabd4-109">Поэтому имя процедуры или свойства не имеет особого смысла в `Set` процедура и в ней нельзя хранить значения.</span><span class="sxs-lookup"><span data-stu-id="fabd4-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="fabd4-110">В следующем примере показано подход, который может вызвать эту ошибку, следуют рекомендуемый подход.</span><span class="sxs-lookup"><span data-stu-id="fabd4-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="fabd4-111">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="fabd4-111">By default, this message is a warning.</span></span> <span data-ttu-id="fabd4-112">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fabd4-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="fabd4-113">**Идентификатор ошибки:** BC42026</span><span class="sxs-lookup"><span data-stu-id="fabd4-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fabd4-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fabd4-114">To correct this error</span></span>  
  
-   <span data-ttu-id="fabd4-115">Перепишите определение свойства использовать рекомендуемый подход, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="fabd4-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabd4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fabd4-116">See Also</span></span>  
 <span data-ttu-id="fabd4-117">[Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fabd4-117">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="fabd4-118"> [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="fabd4-118"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="fabd4-119"> [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="fabd4-119"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
