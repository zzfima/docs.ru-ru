---
title: Пространство имен или тип, указанные в свойстве Imports <qualifiedelementname> для проекта, не содержит никаких общих членов или не может быть найдено
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 554300f87dbfca351ebcd2d544051968e84880ab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816831"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="5a18d-102">Пространство имен или тип, указанный в Imports на уровне проекта\<полное_имя_элемента > "не содержат открытые члены или не найден</span><span class="sxs-lookup"><span data-stu-id="5a18d-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="5a18d-103">Пространство имен или тип, указанный в Imports на уровне проекта\<полное_имя_элемента > "не содержат открытые члены или не найден.</span><span class="sxs-lookup"><span data-stu-id="5a18d-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="5a18d-104">Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член.</span><span class="sxs-lookup"><span data-stu-id="5a18d-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="5a18d-105">Убедитесь, что псевдоним не может содержать другие псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="5a18d-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="5a18d-106">Свойство импорта проекта указывает содержащий элемент, который не может быть найден или не определяет никакие `Public` членов.</span><span class="sxs-lookup"><span data-stu-id="5a18d-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="5a18d-107">Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления.</span><span class="sxs-lookup"><span data-stu-id="5a18d-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="5a18d-108">Содержащий элемент содержит элементы, такие как переменные, процедуры или другие содержащие элементы.</span><span class="sxs-lookup"><span data-stu-id="5a18d-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="5a18d-109">Импорт нужен, чтобы код для доступа к членам пространства имен или типа без уточнения их.</span><span class="sxs-lookup"><span data-stu-id="5a18d-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="5a18d-110">Проект также может потребоваться добавить ссылку на пространство имен или тип.</span><span class="sxs-lookup"><span data-stu-id="5a18d-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="5a18d-111">Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="5a18d-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="5a18d-112">Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые ее используют.</span><span class="sxs-lookup"><span data-stu-id="5a18d-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="5a18d-113">Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешной.</span><span class="sxs-lookup"><span data-stu-id="5a18d-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="5a18d-114">В любом случае не имеет смысла в импорте элемента.</span><span class="sxs-lookup"><span data-stu-id="5a18d-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="5a18d-115">Использовании **конструктор проектов** для указания элементов для импорта.</span><span class="sxs-lookup"><span data-stu-id="5a18d-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="5a18d-116">Используйте **импортированные пространства имен** раздел **ссылки** страницы.</span><span class="sxs-lookup"><span data-stu-id="5a18d-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="5a18d-117">Можно перейти к **конструктор проектов** , дважды щелкнув **Мой проект** значок в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="5a18d-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="5a18d-118">**Идентификатор ошибки:** BC40057</span><span class="sxs-lookup"><span data-stu-id="5a18d-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a18d-119">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5a18d-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="5a18d-120">Откройте **конструктор проектов** и переключиться в режим **ссылку** страницы.</span><span class="sxs-lookup"><span data-stu-id="5a18d-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="5a18d-121">В **импортированные пространства имен** разделе, убедитесь, что содержащий элемент доступен из проекта.</span><span class="sxs-lookup"><span data-stu-id="5a18d-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="5a18d-122">Убедитесь, что элемент, имеющий предоставляет по крайней мере `Public` член.</span><span class="sxs-lookup"><span data-stu-id="5a18d-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a18d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5a18d-123">See also</span></span>

- [<span data-ttu-id="5a18d-124">Страница "Ссылки" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a18d-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="5a18d-125">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="5a18d-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="5a18d-126">Public</span><span class="sxs-lookup"><span data-stu-id="5a18d-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="5a18d-127">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a18d-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="5a18d-128">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="5a18d-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
