---
title: Имя <namespacename> в корневом пространстве имен <fullnamespacename> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 821044d3ee359a052fa6a763e9c5a89da5d6f607
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775580"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="d8a15-102">Имя \<namespacename > в корневом пространстве имен \<fullnamespacename > несовместимо с CLS</span><span class="sxs-lookup"><span data-stu-id="d8a15-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="d8a15-103">Сборка помечается как `<CLSCompliant(True)>`, но элемент имени корневого пространства имен начинается с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="d8a15-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="d8a15-104">Программный элемент может содержать один или несколько символов подчеркивания, но для соответствия [языковым независимостьм и зависимым от языка компонентам](../../../standard/language-independence-and-language-independent-components.md) (CLS) он не должен начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d8a15-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="d8a15-105">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d8a15-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="d8a15-106">Когда вы применяете атрибут <xref:System.CLSCompliantAttribute> к программному элементу, вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать на совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="d8a15-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="d8a15-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="d8a15-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="d8a15-108">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="d8a15-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="d8a15-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="d8a15-109">By default, this message is a warning.</span></span> <span data-ttu-id="d8a15-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d8a15-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d8a15-111">**Идентификатор ошибки:** BC40039</span><span class="sxs-lookup"><span data-stu-id="d8a15-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8a15-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d8a15-112">To correct this error</span></span>  
  
- <span data-ttu-id="d8a15-113">Если требуется совместимость с CLS, измените имя корневого пространства имен так, чтобы ни один из его элементов не начинался с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d8a15-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="d8a15-114">Если требуется, чтобы имя пространства имен оставалось без изменений, удалите <xref:System.CLSCompliantAttribute> из сборки или пометьте его как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="d8a15-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a15-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d8a15-115">See also</span></span>

- [<span data-ttu-id="d8a15-116">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="d8a15-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="d8a15-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8a15-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="d8a15-118">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="d8a15-118">-rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="d8a15-119">Страница "Приложение" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8a15-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="d8a15-120">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="d8a15-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="d8a15-121">Соглашения об именовании Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8a15-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
