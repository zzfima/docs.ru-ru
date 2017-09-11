---
title: "Имя &lt;namespacename&gt; в корневом пространстве имен &lt;fullnamespacename&gt; не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
dev_langs:
- VB
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
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
ms.openlocfilehash: 0d31657a958581b91cb448b78b8f55f8aadfe7c9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="51809-102">Имя &lt;namespacename&gt; в корневом пространстве имен &lt;fullnamespacename&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="51809-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="51809-103">Сборка помечена как `<CLSCompliant(True)>`, но элемент корневого пространства имен начинается со знака подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="51809-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="51809-104">Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), оно не должно начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="51809-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="51809-105">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="51809-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="51809-106">При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="51809-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="51809-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="51809-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="51809-108">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="51809-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="51809-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="51809-109">By default, this message is a warning.</span></span> <span data-ttu-id="51809-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="51809-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="51809-111">**Идентификатор ошибки:** BC40039</span><span class="sxs-lookup"><span data-stu-id="51809-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51809-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="51809-112">To correct this error</span></span>  
  
-   <span data-ttu-id="51809-113">Если требуется CLS-совместимость, измените корневого пространства имен, чтобы ни один из его элементов начинается со знака подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="51809-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="51809-114">Если требуется, имя пространства имен осталось неизменными, удалите <xref:System.CLSCompliantAttribute>из сборки или пометьте его как `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="51809-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51809-115">См. также</span><span class="sxs-lookup"><span data-stu-id="51809-115">See Also</span></span>  
 <span data-ttu-id="51809-116">[Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="51809-116">[Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="51809-117"> [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="51809-117"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="51809-118"> [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/rootnamespace.md) </span><span class="sxs-lookup"><span data-stu-id="51809-118"> [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md) </span></span>  
<span data-ttu-id="51809-119"> [Страница "Приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="51809-119"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="51809-120"> [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="51809-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="51809-121"> [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="51809-121"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="51809-122"> [\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="51809-122"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
