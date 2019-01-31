---
title: Имя <namespacename> в корневом пространстве имен <fullnamespacename> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: c5afdcc98b7acb1927c9b0735a69fbe64c3d8e60
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268721"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="5a883-102">Имя \<Имя_пространства_имен > в корневом пространстве имен \<fullnamespacename > не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="5a883-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="5a883-103">Сборка помечена как `<CLSCompliant(True)>`, но элемент корневое пространство имен начинается с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="5a883-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="5a883-104">Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он не должен начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5a883-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="5a883-105">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5a883-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="5a883-106">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="5a883-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="5a883-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="5a883-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="5a883-108">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="5a883-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="5a883-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="5a883-109">By default, this message is a warning.</span></span> <span data-ttu-id="5a883-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5a883-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5a883-111">**Идентификатор ошибки:** BC40039</span><span class="sxs-lookup"><span data-stu-id="5a883-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a883-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5a883-112">To correct this error</span></span>  
  
-   <span data-ttu-id="5a883-113">Если требуется CLS-совместимость, измените имя корневого пространства имен, чтобы ни один из его элементов начинается с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5a883-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="5a883-114">Если вам требуется, что имя пространства имен остаются неизменными, то удалите <xref:System.CLSCompliantAttribute> из сборки или пометьте его как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="5a883-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a883-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5a883-115">See also</span></span>
- [<span data-ttu-id="5a883-116">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="5a883-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="5a883-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a883-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="5a883-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="5a883-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="5a883-119">Страница "Приложение" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a883-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="5a883-120">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="5a883-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="5a883-121">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a883-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

