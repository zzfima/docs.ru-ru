---
title: Пространство имен или тип, указанный в Imports <qualifiedelementname>, не содержит общих членов или не найден
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: d19a769b33b3b63b7f431b73841f49632e41f9e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288279"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="be29d-102">Пространство имен или тип, указанный в Imports\<полное_имя_элемента > "не содержат открытые члены или не найден</span><span class="sxs-lookup"><span data-stu-id="be29d-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="be29d-103">Пространство имен или тип, указанный в Imports\<полное_имя_элемента > "не содержат открытые члены или не найден.</span><span class="sxs-lookup"><span data-stu-id="be29d-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="be29d-104">Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член.</span><span class="sxs-lookup"><span data-stu-id="be29d-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="be29d-105">Убедитесь, что псевдоним не может содержать другие псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="be29d-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="be29d-106">`Imports` Инструкция указывает содержащий элемент, который не может быть найден или не определяет никакие `Public` членов.</span><span class="sxs-lookup"><span data-stu-id="be29d-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="be29d-107">Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления.</span><span class="sxs-lookup"><span data-stu-id="be29d-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="be29d-108">Содержащий элемент содержит элементы, такие как переменные, процедуры или другие содержащие элементы.</span><span class="sxs-lookup"><span data-stu-id="be29d-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="be29d-109">Импорт нужен, чтобы код для доступа к членам пространства имен или типа без уточнения их.</span><span class="sxs-lookup"><span data-stu-id="be29d-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="be29d-110">Проект также может потребоваться добавить ссылку на пространство имен или тип.</span><span class="sxs-lookup"><span data-stu-id="be29d-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="be29d-111">Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="be29d-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="be29d-112">Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые ее используют.</span><span class="sxs-lookup"><span data-stu-id="be29d-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="be29d-113">Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешной.</span><span class="sxs-lookup"><span data-stu-id="be29d-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="be29d-114">В любом случае не имеет смысла в импорте элемента.</span><span class="sxs-lookup"><span data-stu-id="be29d-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="be29d-115">Имейте в виду, что если импортировать элемент и назначить псевдоним импорта, то нельзя использовать этот псевдоним импорта для импорта другого элемента.</span><span class="sxs-lookup"><span data-stu-id="be29d-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="be29d-116">Следующий код приводит к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="be29d-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="be29d-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="be29d-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="be29d-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="be29d-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="be29d-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="be29d-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="be29d-120">**Идентификатор ошибки:** BC40056</span><span class="sxs-lookup"><span data-stu-id="be29d-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be29d-121">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="be29d-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="be29d-122">Убедитесь, что содержащий элемент доступен из проекта.</span><span class="sxs-lookup"><span data-stu-id="be29d-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="be29d-123">Убедитесь, что спецификация содержащего его элемента содержит псевдоним импорта из другой операции импорта.</span><span class="sxs-lookup"><span data-stu-id="be29d-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="be29d-124">Убедитесь, что элемент, имеющий предоставляет по крайней мере `Public` член.</span><span class="sxs-lookup"><span data-stu-id="be29d-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be29d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="be29d-125">See also</span></span>
- [<span data-ttu-id="be29d-126">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="be29d-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="be29d-127">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="be29d-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="be29d-128">Public</span><span class="sxs-lookup"><span data-stu-id="be29d-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="be29d-129">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be29d-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="be29d-130">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="be29d-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
