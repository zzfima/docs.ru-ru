---
title: Выражение рекурсивно вызывает содержащее свойство <propertyname>
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 93d02618ff19f431b3602e74478337f6918df289
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665169"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="9494d-102">Выражение рекурсивно вызывает содержащее его свойство "\<имя_свойства >"</span><span class="sxs-lookup"><span data-stu-id="9494d-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="9494d-103">Оператор в `Set` процедуры определения свойства сохраняет значение в имени свойства.</span><span class="sxs-lookup"><span data-stu-id="9494d-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="9494d-104">Рекомендуемый подход для хранения значений свойства является определение `Private` переменных в контейнере свойства и его использования в языках `Get` и `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="9494d-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="9494d-105">`Set` Процедура затем будет хранить входящее значение в этом `Private` переменной.</span><span class="sxs-lookup"><span data-stu-id="9494d-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="9494d-106">`Get` Процедура действует как `Function` процедуры, поэтому можно присвоить значение имени свойства и вернуть управление путем добавления `End Get` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9494d-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="9494d-107">Тем не менее рекомендуется включать `Private` переменной в качестве значения [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9494d-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="9494d-108">`Set` Процедура действует как `Sub` процедуры, которая не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="9494d-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="9494d-109">Таким образом, имя процедуры или свойства не имеет специального значения в пределах `Set` процедура и в ней нельзя хранить значение.</span><span class="sxs-lookup"><span data-stu-id="9494d-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="9494d-110">В следующем примере показано подход, который может вызывать эту ошибку, следуют рекомендуемый подход.</span><span class="sxs-lookup"><span data-stu-id="9494d-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
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
  
 <span data-ttu-id="9494d-111">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="9494d-111">By default, this message is a warning.</span></span> <span data-ttu-id="9494d-112">Дополнительные сведения о скрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9494d-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9494d-113">**Идентификатор ошибки:** BC42026</span><span class="sxs-lookup"><span data-stu-id="9494d-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9494d-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9494d-114">To correct this error</span></span>  
  
- <span data-ttu-id="9494d-115">Перепишите определение свойства использовать рекомендуемый подход, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="9494d-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9494d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9494d-116">See also</span></span>

- [<span data-ttu-id="9494d-117">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="9494d-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="9494d-118">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="9494d-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="9494d-119">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="9494d-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
