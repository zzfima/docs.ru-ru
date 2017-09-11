---
title: "Имя &lt;membername&gt; не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
dev_langs:
- VB
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
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
ms.openlocfilehash: cbe0a8db6d801a0d083a6828af75342f15f0178d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="5727f-102">Имя &lt;membername&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="5727f-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="5727f-103">Сборка помечена как `<CLSCompliant(True)>` , но предоставляет член с именем, начинающимся со знака подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="5727f-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="5727f-104">Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), оно не должно начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5727f-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="5727f-105">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5727f-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="5727f-106">При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="5727f-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="5727f-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="5727f-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="5727f-108">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="5727f-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="5727f-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="5727f-109">By default, this message is a warning.</span></span> <span data-ttu-id="5727f-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5727f-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5727f-111">**Идентификатор ошибки:** BC40031</span><span class="sxs-lookup"><span data-stu-id="5727f-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5727f-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5727f-112">To correct this error</span></span>  
  
-   <span data-ttu-id="5727f-113">Если имеется контроль над исходным кодом, измените имя элемента, чтобы он не начинается с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5727f-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="5727f-114">Если требуется, чтобы имя члена осталось неизменными, удалите <xref:System.CLSCompliantAttribute>из его определения или пометьте его как `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="5727f-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="5727f-115">Можно также пометить сборку как `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="5727f-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5727f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5727f-116">See Also</span></span>  
 <span data-ttu-id="5727f-117">[Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="5727f-117">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="5727f-118"> [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="5727f-118"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="5727f-119"> [\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="5727f-119"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
