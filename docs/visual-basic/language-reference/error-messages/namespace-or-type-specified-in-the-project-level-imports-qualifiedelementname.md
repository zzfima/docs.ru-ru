---
title: "Пространство имен или тип, указанный в Imports на уровне проекта&lt;qualifiedelementname&gt;&quot;не содержит никаких общих членов или не удается найти | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
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
ms.openlocfilehash: 301e2bd419f0b4723ff76c2bdd2187c4c412e174
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="6b7e1-102">Пространство имен или тип, указанный в Imports на уровне проекта&lt;qualifiedelementname&gt;"не содержит никаких общих членов или не найден</span><span class="sxs-lookup"><span data-stu-id="6b7e1-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="6b7e1-103">Пространство имен или тип, указанный в Imports на уровне проекта\<qualifiedelementname настроек "не содержит никаких общих членов или не найден.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="6b7e1-104">Убедитесь, что пространство имен или тип определен и содержит хотя бы один открытый член.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="6b7e1-105">Убедитесь, что имя псевдонима не содержит других псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="6b7e1-106">Свойство импорта для проекта указывает содержащий элемент, который не может быть найден или не определяет никаких `Public` члены.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="6b7e1-107">Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="6b7e1-108">Содержащий элемент содержит элементы, такие как переменные, процедуры или другие содержащие элементы.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="6b7e1-109">Импорт нужен, чтобы код для доступа к членам пространства имен или типа без их уточнения.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="6b7e1-110">Проект может также потребоваться добавить ссылку на пространство имен или тип.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="6b7e1-111">Дополнительные сведения см. в разделе «Импорт содержащих элементов» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="6b7e1-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="6b7e1-112">Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="6b7e1-113">Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешной.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="6b7e1-114">В любом случае нет смысла в импорте элемента.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="6b7e1-115">Использовать **конструктора проектов** позволяет указать элементы для импорта.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="6b7e1-116">Используйте **импортированные пространства имен** раздел **ссылки** страницы.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="6b7e1-117">Можно получить **конструктора проектов** , дважды щелкнув **Мой проект** значок в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="6b7e1-118">**Идентификатор ошибки:** BC40057</span><span class="sxs-lookup"><span data-stu-id="6b7e1-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b7e1-119">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6b7e1-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="6b7e1-120">Откройте **конструктора проектов** и переключитесь в **ссылки** страницы.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="6b7e1-121">В **импортированные пространства имен** убедитесь, что содержащий элемент доступен из проекта.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="6b7e1-122">Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` член.</span><span class="sxs-lookup"><span data-stu-id="6b7e1-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7e1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6b7e1-123">See Also</span></span>  
 <span data-ttu-id="6b7e1-124">[Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="6b7e1-124">[References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="6b7e1-125"> [NIB Практическое руководство: изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="6b7e1-125"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="6b7e1-126"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="6b7e1-126"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="6b7e1-127"> [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="6b7e1-127"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="6b7e1-128"> [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="6b7e1-128"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
