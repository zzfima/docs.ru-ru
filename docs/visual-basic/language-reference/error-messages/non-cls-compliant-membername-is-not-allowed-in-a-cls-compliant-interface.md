---
title: "Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимый интерфейс"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 358abd338d3ce780c2f0aae7aa8efb53e57b477c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="74d48-102">Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимый интерфейс</span><span class="sxs-lookup"><span data-stu-id="74d48-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="74d48-103">Свойство, процедура или событие в интерфейсе помечен как `<CLSCompliant(True)>` когда сам интерфейс помечен как `<CLSCompliant(False)>` или не отмечен.</span><span class="sxs-lookup"><span data-stu-id="74d48-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="74d48-104">Для интерфейса в соответствии с [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), все члены должны быть совместимыми.</span><span class="sxs-lookup"><span data-stu-id="74d48-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="74d48-105">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="74d48-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="74d48-106">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="74d48-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="74d48-107">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="74d48-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="74d48-108">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="74d48-108">By default, this message is a warning.</span></span> <span data-ttu-id="74d48-109">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="74d48-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="74d48-110">**Идентификатор ошибки:** BC40033</span><span class="sxs-lookup"><span data-stu-id="74d48-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74d48-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="74d48-111">To correct this error</span></span>  
  
-   <span data-ttu-id="74d48-112">Если необходима CLS-совместимость и имеется контроль над исходным кодом интерфейса, пометьте интерфейс как `<CLSCompliant(True)>` Если все его члены являются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="74d48-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="74d48-113">Если требуется совместимость с CLS и вы можете управлять исходным кодом интерфейса, или он не квалифицирован как совместимый, определите этот член внутри другого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="74d48-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="74d48-114">Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="74d48-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d48-115">См. также</span><span class="sxs-lookup"><span data-stu-id="74d48-115">See Also</span></span>  
 [<span data-ttu-id="74d48-116">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="74d48-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="74d48-117">\<PAVE НАД > написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="74d48-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
