---
title: "Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимом интерфейсе | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
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
ms.openlocfilehash: 27e83344c68d73c992d2395ab5d1bfcdb67520b0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="ccc1a-102">Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="ccc1a-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="ccc1a-103">Свойство, процедура или событие в интерфейсе помечен как `<CLSCompliant(True)>` при сам интерфейс помечен как `<CLSCompliant(False)>` или не отмечен.</span><span class="sxs-lookup"><span data-stu-id="ccc1a-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="ccc1a-104">Для интерфейса в соответствии с [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), все его члены должны быть совместимыми.</span><span class="sxs-lookup"><span data-stu-id="ccc1a-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="ccc1a-105">При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="ccc1a-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="ccc1a-106">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="ccc1a-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="ccc1a-107">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="ccc1a-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="ccc1a-108">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="ccc1a-108">By default, this message is a warning.</span></span> <span data-ttu-id="ccc1a-109">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ccc1a-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ccc1a-110">**Идентификатор ошибки:** BC40033</span><span class="sxs-lookup"><span data-stu-id="ccc1a-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ccc1a-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ccc1a-111">To correct this error</span></span>  
  
-   <span data-ttu-id="ccc1a-112">Если требуется CLS-совместимость и имеется контроль над всем исходным кодом интерфейса, пометьте интерфейс как `<CLSCompliant(True)>` Если все его члены являются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="ccc1a-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="ccc1a-113">Если требуется CLS-совместимость и нет контроля над всем исходным кодом интерфейса, или он не определен как совместимый, определите этот член внутри другого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ccc1a-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="ccc1a-114">Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute>из его определения или пометьте его как `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="ccc1a-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc1a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ccc1a-115">See Also</span></span>  
 <span data-ttu-id="ccc1a-116">[Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ccc1a-116">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="ccc1a-117"> [\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="ccc1a-117"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
