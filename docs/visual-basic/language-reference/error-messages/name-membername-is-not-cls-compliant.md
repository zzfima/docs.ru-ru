---
title: Имя &lt;membername&gt; не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 26ff13de461d5a96724868b7928129a326cdf1d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="3a954-102">Имя &lt;membername&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="3a954-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="3a954-103">Сборка помечена как `<CLSCompliant(True)>` , но предоставляет член с именем, которое начинается со знака подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="3a954-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="3a954-104">Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он не должен начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="3a954-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="3a954-105">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="3a954-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="3a954-106">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="3a954-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="3a954-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="3a954-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="3a954-108">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="3a954-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="3a954-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="3a954-109">By default, this message is a warning.</span></span> <span data-ttu-id="3a954-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3a954-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3a954-111">**Идентификатор ошибки:** BC40031</span><span class="sxs-lookup"><span data-stu-id="3a954-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a954-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3a954-112">To correct this error</span></span>  
  
-   <span data-ttu-id="3a954-113">Если вы можете управлять исходным кодом, измените имя члена, чтобы он не начинается с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="3a954-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="3a954-114">Если требуется, чтобы имя члена осталось неизменными, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="3a954-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="3a954-115">Можно также пометить сборку как `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="3a954-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a954-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3a954-116">See Also</span></span>  
 [<span data-ttu-id="3a954-117">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="3a954-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="3a954-118">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a954-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  

