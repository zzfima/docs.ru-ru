---
title: Пространство имен или тип, указанный в Imports &#39; &lt;qualifiedelementname&gt;&#39; &#39; t содержат публичных членов или не найден
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="781ae-102">Пространство имен или тип, указанный в Imports &#39; &lt;qualifiedelementname&gt;&#39; &#39; t содержат публичных членов или не найден</span><span class="sxs-lookup"><span data-stu-id="781ae-102">Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="781ae-103">Пространство имен или тип, указанный в Imports\<qualifiedelementname > "не содержат публичных членов или не найден.</span><span class="sxs-lookup"><span data-stu-id="781ae-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="781ae-104">Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член.</span><span class="sxs-lookup"><span data-stu-id="781ae-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="781ae-105">Убедитесь, что имя псевдонима не содержит других псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="781ae-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="781ae-106">`Imports` Инструкция указывает содержащий элемент, который не может быть найден или не определяет никакие `Public` члены.</span><span class="sxs-lookup"><span data-stu-id="781ae-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="781ae-107">Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления.</span><span class="sxs-lookup"><span data-stu-id="781ae-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="781ae-108">Элемент-контейнер содержит элементы, такие как переменные, процедуры или другие содержащие элементы.</span><span class="sxs-lookup"><span data-stu-id="781ae-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="781ae-109">Импорт предназначено для обеспечения кода для доступа к членам пространства имен или типа без их уточнения.</span><span class="sxs-lookup"><span data-stu-id="781ae-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="781ae-110">Проект также может потребоваться добавить ссылку на пространство имен или тип.</span><span class="sxs-lookup"><span data-stu-id="781ae-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="781ae-111">Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="781ae-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="781ae-112">Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="781ae-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="781ae-113">Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешно.</span><span class="sxs-lookup"><span data-stu-id="781ae-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="781ae-114">В любом случае нет смысла в импорте элемента.</span><span class="sxs-lookup"><span data-stu-id="781ae-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="781ae-115">Имейте в виду, что если импортировать содержащий элемент и присвоить псевдоним импорта, затем нельзя использовать этот псевдоним импорта для импорта другого элемента.</span><span class="sxs-lookup"><span data-stu-id="781ae-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="781ae-116">Следующий код создает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="781ae-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="781ae-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="781ae-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="781ae-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="781ae-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="781ae-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="781ae-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="781ae-120">**Идентификатор ошибки:** BC40056</span><span class="sxs-lookup"><span data-stu-id="781ae-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="781ae-121">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="781ae-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="781ae-122">Убедитесь, что содержащий его элемент доступен из проекта.</span><span class="sxs-lookup"><span data-stu-id="781ae-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="781ae-123">Убедитесь, что спецификация содержащего его элемента содержит псевдоним импорта из другого импорта.</span><span class="sxs-lookup"><span data-stu-id="781ae-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="781ae-124">Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` член.</span><span class="sxs-lookup"><span data-stu-id="781ae-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781ae-125">См. также</span><span class="sxs-lookup"><span data-stu-id="781ae-125">See Also</span></span>  
 [<span data-ttu-id="781ae-126">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="781ae-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="781ae-127">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="781ae-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="781ae-128">Public</span><span class="sxs-lookup"><span data-stu-id="781ae-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="781ae-129">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="781ae-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="781ae-130">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="781ae-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
