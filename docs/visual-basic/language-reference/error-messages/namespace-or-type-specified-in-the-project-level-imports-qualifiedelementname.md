---
title: Пространство имен или тип, указанный в Imports уровня проекта &#39; &lt;qualifiedelementname&gt; &#39; &#39;t содержат публичных членов или не найден
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="41ed7-102">Пространство имен или тип, указанный в Imports уровня проекта &#39; &lt;qualifiedelementname&gt; &#39; &#39;t содержат публичных членов или не найден</span><span class="sxs-lookup"><span data-stu-id="41ed7-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="41ed7-103">Пространство имен или тип, указанный в операции импорта на уровне проекта\<qualifiedelementname > "не содержат публичных членов или не найден.</span><span class="sxs-lookup"><span data-stu-id="41ed7-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="41ed7-104">Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член.</span><span class="sxs-lookup"><span data-stu-id="41ed7-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="41ed7-105">Убедитесь, что имя псевдонима не содержит других псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="41ed7-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="41ed7-106">Указывает свойство импорта проекта, содержащий элемент, который не может быть найден или не определяет никакие `Public` члены.</span><span class="sxs-lookup"><span data-stu-id="41ed7-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="41ed7-107">Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления.</span><span class="sxs-lookup"><span data-stu-id="41ed7-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="41ed7-108">Элемент-контейнер содержит элементы, такие как переменные, процедуры или другие содержащие элементы.</span><span class="sxs-lookup"><span data-stu-id="41ed7-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="41ed7-109">Импорт предназначено для обеспечения кода для доступа к членам пространства имен или типа без их уточнения.</span><span class="sxs-lookup"><span data-stu-id="41ed7-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="41ed7-110">Проект также может потребоваться добавить ссылку на пространство имен или тип.</span><span class="sxs-lookup"><span data-stu-id="41ed7-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="41ed7-111">Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="41ed7-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="41ed7-112">Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="41ed7-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="41ed7-113">Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешно.</span><span class="sxs-lookup"><span data-stu-id="41ed7-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="41ed7-114">В любом случае нет смысла в импорте элемента.</span><span class="sxs-lookup"><span data-stu-id="41ed7-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="41ed7-115">Вы используете **конструктора проектов** указывать элементы для импорта.</span><span class="sxs-lookup"><span data-stu-id="41ed7-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="41ed7-116">Используйте **импортированные пространства имен** раздел **ссылки** страницы.</span><span class="sxs-lookup"><span data-stu-id="41ed7-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="41ed7-117">Можно получить **конструктора проектов** , дважды щелкнув **Мой проект** значок в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="41ed7-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="41ed7-118">**Идентификатор ошибки:** BC40057</span><span class="sxs-lookup"><span data-stu-id="41ed7-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41ed7-119">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="41ed7-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="41ed7-120">Откройте **конструктора проектов** и переключитесь в **ссылки** страницы.</span><span class="sxs-lookup"><span data-stu-id="41ed7-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="41ed7-121">В **импортированные пространства имен** убедитесь, что содержащий его элемент доступен из проекта.</span><span class="sxs-lookup"><span data-stu-id="41ed7-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="41ed7-122">Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` член.</span><span class="sxs-lookup"><span data-stu-id="41ed7-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ed7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="41ed7-123">See Also</span></span>  
 [<span data-ttu-id="41ed7-124">Страница "Ссылки" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41ed7-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [<span data-ttu-id="41ed7-125">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="41ed7-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="41ed7-126">Public</span><span class="sxs-lookup"><span data-stu-id="41ed7-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="41ed7-127">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41ed7-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="41ed7-128">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="41ed7-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
