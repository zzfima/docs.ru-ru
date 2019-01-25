---
title: Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 9caf02907e4b6de4c2bd8de778d4ad7a9320a82b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690583"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="e26b2-102">Разрешение позднего связывания; возможно возникновение ошибок времени выполнения</span><span class="sxs-lookup"><span data-stu-id="e26b2-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="e26b2-103">Объект присваивается переменной, объявленной с [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="e26b2-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="e26b2-104">При объявлении переменной как `Object`, компилятор должен осуществить *позднее связывание*, что вызывает дополнительные операции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e26b2-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="e26b2-105">Это также подвергает приложение риску возникновения ошибок времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e26b2-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="e26b2-106">Например, если вы назначаете <xref:System.Windows.Forms.Form> для `Object` переменной и затем пытаемся обратиться к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> свойство, среда выполнения создает <xref:System.MemberAccessException> поскольку <xref:System.Windows.Forms.Form> класс не предоставляет `NameTable` свойство.</span><span class="sxs-lookup"><span data-stu-id="e26b2-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="e26b2-107">Если вы объявляете переменную определенного типа, компилятор может выполнять *раннее связывание* во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="e26b2-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="e26b2-108">Это позволяет повысить производительность, управляемый доступ к членами определенного типа и лучшей читаемости кода.</span><span class="sxs-lookup"><span data-stu-id="e26b2-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="e26b2-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="e26b2-109">By default, this message is a warning.</span></span> <span data-ttu-id="e26b2-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e26b2-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e26b2-111">**Идентификатор ошибки:** BC42017</span><span class="sxs-lookup"><span data-stu-id="e26b2-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e26b2-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e26b2-112">To correct this error</span></span>  
  
-   <span data-ttu-id="e26b2-113">Если это возможно следует объявите переменную с определенным типом.</span><span class="sxs-lookup"><span data-stu-id="e26b2-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26b2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e26b2-114">See also</span></span>
- [<span data-ttu-id="e26b2-115">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="e26b2-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="e26b2-116">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="e26b2-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
