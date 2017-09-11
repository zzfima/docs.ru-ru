---
title: "Ссылки и оператор Imports (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
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
ms.openlocfilehash: 4c6ce65005f84317c96a1124d609c46734d3cc66
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="d2778-102">Ссылки и оператор Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2778-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="d2778-103">Вы внешние объекты можно сделать доступными для проекта, выбрав **добавить ссылку** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="d2778-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="d2778-104">Ссылки в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] могут указывать на сборки, которые подобны библиотекам типов, но содержат больше сведений.</span><span class="sxs-lookup"><span data-stu-id="d2778-104">References in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="d2778-105">Оператор Imports</span><span class="sxs-lookup"><span data-stu-id="d2778-105">The Imports Statement</span></span>  
 <span data-ttu-id="d2778-106">Сборки содержат один или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="d2778-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="d2778-107">При добавлении ссылки на сборку, можно добавить `Imports` инструкции к модулю, управляющему видимостью пространств имен этой сборки в данном модуле.</span><span class="sxs-lookup"><span data-stu-id="d2778-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="d2778-108">`Imports` Инструкция предоставляет контекст области видимости, что позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.</span><span class="sxs-lookup"><span data-stu-id="d2778-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="d2778-109">`Imports` Инструкция имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d2778-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="d2778-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="d2778-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="d2778-111">`Aliasname`ссылается на короткое имя, которое можно использовать в коде для ссылки на импортируемое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d2778-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="d2778-112">`Namespace`— Это пространство имен, доступное либо через ссылку на проект, через определение в проекте, либо через предыдущим `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2778-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="d2778-113">Модуль может содержать любое количество `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2778-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="d2778-114">Они должны располагаться после `Option` инструкций, если он присутствует, но перед любым другим кодом.</span><span class="sxs-lookup"><span data-stu-id="d2778-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2778-115">Не следует путать ссылки на проекты с `Imports` инструкции или `Declare` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2778-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="d2778-116">Ссылки на проекты делают внешние объекты, такие как объекты в сборках, доступные для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проектов.</span><span class="sxs-lookup"><span data-stu-id="d2778-116">Project references make external objects, such as objects in assemblies, available to [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] projects.</span></span> <span data-ttu-id="d2778-117">`Imports` Инструкция используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам.</span><span class="sxs-lookup"><span data-stu-id="d2778-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="d2778-118">`Declare` Инструкция используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="d2778-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="d2778-119">Использование псевдонимов при помощи оператора Imports</span><span class="sxs-lookup"><span data-stu-id="d2778-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="d2778-120">`Imports` Инструкция облегчает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок.</span><span class="sxs-lookup"><span data-stu-id="d2778-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="d2778-121">Псевдонимы позволяют присваивать более понятные имена только одной части пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d2778-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="d2778-122">Например, возврат каретки и перевод строки последовательность, которая единый фрагмент текста, отображаемого на нескольких строках является частью <xref:Microsoft.VisualBasic.ControlChars>модуля в <xref:Microsoft.VisualBasic?displayProperty=fullName>имен.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="d2778-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="d2778-123">Для использования этой константы в программе без псевдонима, потребовалось бы введите следующий код:</span><span class="sxs-lookup"><span data-stu-id="d2778-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 <span data-ttu-id="d2778-124">[!code-vb[VbVbalrApplication&#3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d2778-124">[!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="d2778-125">`Imports`инструкции должны всегда быть сразу же после первой строки `Option` инструкции в модуле.</span><span class="sxs-lookup"><span data-stu-id="d2778-125">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="d2778-126">В следующем фрагменте кода показано, как импортировать и присваивать псевдоним <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>модуля:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d2778-126">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName> module:</span></span>  
  
 <span data-ttu-id="d2778-127">[!code-vb[VbVbalrApplication&#4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d2778-127">[!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="d2778-128">Будущие ссылки на это пространство имен может быть значительно более краткими:</span><span class="sxs-lookup"><span data-stu-id="d2778-128">Future references to this namespace can be considerably shorter:</span></span>  
  
 <span data-ttu-id="d2778-129">[!code-vb[VbVbalrApplication&#5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="d2778-129">[!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="d2778-130">Если `Imports` инструкции псевдоним не включен, элементы, определенные в импортированном пространстве имен, которые могут использоваться в модуле без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="d2778-130">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="d2778-131">Если указано имя псевдонима, он должен использоваться как квалификатор имен, содержащихся в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="d2778-131">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2778-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d2778-132">See Also</span></span>  
 <span data-ttu-id="d2778-133"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="d2778-133"><xref:Microsoft.VisualBasic.ControlChars></span></span>   
 <span data-ttu-id="d2778-134"><xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic></span><span class="sxs-lookup"><span data-stu-id="d2778-134"><xref:Microsoft.VisualBasic></span></span>   
<span data-ttu-id="d2778-135"> [NIB. Практическое руководство. Добавление и удаление ссылок с помощью диалогового окна "Добавление ссылки"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="d2778-135"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="d2778-136"> [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="d2778-136"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="d2778-137"> [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="d2778-137"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="d2778-138"> [Практическое руководство: Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="d2778-138"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="d2778-139"> [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="d2778-139"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
