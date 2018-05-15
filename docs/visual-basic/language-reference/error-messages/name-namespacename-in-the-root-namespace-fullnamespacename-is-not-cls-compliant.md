---
title: Имя &lt;namespacename&gt; в корневом пространстве имен &lt;fullnamespacename&gt; не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 0359df132b9760f4f3d05bbece4cdf531efe2136
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="866fd-102">Имя &lt;namespacename&gt; в корневом пространстве имен &lt;fullnamespacename&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="866fd-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="866fd-103">Сборка помечена как `<CLSCompliant(True)>`, но элемент корневого пространства имен начинается со знака подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="866fd-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="866fd-104">Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он не должен начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="866fd-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="866fd-105">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="866fd-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="866fd-106">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="866fd-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="866fd-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="866fd-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="866fd-108">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="866fd-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="866fd-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="866fd-109">By default, this message is a warning.</span></span> <span data-ttu-id="866fd-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="866fd-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="866fd-111">**Идентификатор ошибки:** BC40039</span><span class="sxs-lookup"><span data-stu-id="866fd-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="866fd-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="866fd-112">To correct this error</span></span>  
  
-   <span data-ttu-id="866fd-113">Если требуется CLS-совместимость, измените имя корневого пространства имен, чтобы ни один из его элементов начинается с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="866fd-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="866fd-114">Если требуется, что пространство имен осталось неизменным, удалите <xref:System.CLSCompliantAttribute> из сборки или пометьте его как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="866fd-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866fd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="866fd-115">See Also</span></span>  
 [<span data-ttu-id="866fd-116">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="866fd-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="866fd-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="866fd-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="866fd-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="866fd-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [<span data-ttu-id="866fd-119">Страница "Приложение" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="866fd-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="866fd-120">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="866fd-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="866fd-121">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="866fd-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 
