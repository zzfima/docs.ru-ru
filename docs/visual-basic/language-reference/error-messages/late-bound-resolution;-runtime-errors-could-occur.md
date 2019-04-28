---
title: Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 4fe79c74b6ff634223a4f10d8c5dc54bb77571cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921151"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="66dde-102">Разрешение позднего связывания; возможно возникновение ошибок времени выполнения</span><span class="sxs-lookup"><span data-stu-id="66dde-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="66dde-103">Объект присваивается переменной, объявленной с [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="66dde-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="66dde-104">При объявлении переменной как `Object`, компилятор должен осуществить *позднее связывание*, что вызывает дополнительные операции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="66dde-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="66dde-105">Это также подвергает приложение риску возникновения ошибок времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="66dde-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="66dde-106">Например, если вы назначаете <xref:System.Windows.Forms.Form> для `Object` переменной и затем пытаемся обратиться к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> свойство, среда выполнения создает <xref:System.MemberAccessException> поскольку <xref:System.Windows.Forms.Form> класс не предоставляет `NameTable` свойство.</span><span class="sxs-lookup"><span data-stu-id="66dde-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="66dde-107">Если вы объявляете переменную определенного типа, компилятор может выполнять *раннее связывание* во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="66dde-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="66dde-108">Это позволяет повысить производительность, управляемый доступ к членами определенного типа и лучшей читаемости кода.</span><span class="sxs-lookup"><span data-stu-id="66dde-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="66dde-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="66dde-109">By default, this message is a warning.</span></span> <span data-ttu-id="66dde-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="66dde-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="66dde-111">**Идентификатор ошибки:** BC42017</span><span class="sxs-lookup"><span data-stu-id="66dde-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66dde-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="66dde-112">To correct this error</span></span>  
  
- <span data-ttu-id="66dde-113">Если это возможно следует объявите переменную с определенным типом.</span><span class="sxs-lookup"><span data-stu-id="66dde-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66dde-114">См. также</span><span class="sxs-lookup"><span data-stu-id="66dde-114">See also</span></span>

- [<span data-ttu-id="66dde-115">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="66dde-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="66dde-116">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="66dde-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
