---
title: Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимом интерфейсе
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: c837065d2d448fc2523cfbd18efac962445f8bf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627701"
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="bab1d-102">Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="bab1d-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="bab1d-103">Свойство, процедура или событие в интерфейсе помечен как `<CLSCompliant(True)>` когда сам интерфейс помечен как `<CLSCompliant(False)>` или не помеченный совсем.</span><span class="sxs-lookup"><span data-stu-id="bab1d-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="bab1d-104">Для интерфейса на соответствие стандарту [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), все его члены должны быть совместимыми.</span><span class="sxs-lookup"><span data-stu-id="bab1d-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="bab1d-105">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="bab1d-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="bab1d-106">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="bab1d-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="bab1d-107">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="bab1d-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="bab1d-108">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="bab1d-108">By default, this message is a warning.</span></span> <span data-ttu-id="bab1d-109">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="bab1d-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="bab1d-110">**Идентификатор ошибки:** BC40033</span><span class="sxs-lookup"><span data-stu-id="bab1d-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bab1d-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bab1d-111">To correct this error</span></span>  
  
-   <span data-ttu-id="bab1d-112">Если необходима CLS-совместимость и имеется контроль над исходным кодом интерфейса, пометьте интерфейс как `<CLSCompliant(True)>` Если все его члены являются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="bab1d-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="bab1d-113">Если необходима CLS-совместимость и не можете управлять исходным кодом интерфейса, или он не квалифицирован как совместимый, определите этот член внутри другой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bab1d-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="bab1d-114">Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="bab1d-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab1d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bab1d-115">See also</span></span>
- [<span data-ttu-id="bab1d-116">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="bab1d-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

