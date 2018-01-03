---
title: "Ссылки и оператор Imports (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60c62eae57ae127fcbb860fe72853604802cccd9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="8950f-102">Ссылки и оператор Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8950f-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="8950f-103">Вы внешние объекты можно сделать доступными для проекта, выбрав **добавить ссылку** на **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="8950f-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="8950f-104">Ссылки в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] могут указывать на сборки, которые подобны библиотеки типов, но содержат больше сведений.</span><span class="sxs-lookup"><span data-stu-id="8950f-104">References in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="8950f-105">Оператор Imports</span><span class="sxs-lookup"><span data-stu-id="8950f-105">The Imports Statement</span></span>  
 <span data-ttu-id="8950f-106">Сборки содержат один или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8950f-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="8950f-107">При добавлении ссылки на сборку, можно также добавить `Imports` инструкции к модулю, управляющее видимостью пространств имен этой сборки в модуле.</span><span class="sxs-lookup"><span data-stu-id="8950f-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="8950f-108">`Imports` Инструкция предоставляет контекст области видимости, что позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.</span><span class="sxs-lookup"><span data-stu-id="8950f-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="8950f-109">`Imports` Инструкция имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8950f-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="8950f-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="8950f-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="8950f-111">`Aliasname`ссылается на короткое имя, которое можно использовать в коде для обозначения импортированного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8950f-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="8950f-112">`Namespace`представляет пространство имен, доступное либо через ссылку на проект, через определение в проекте, или предыдущим `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8950f-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="8950f-113">Модуль может содержать любое количество `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8950f-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="8950f-114">Они должны располагаться после `Option` инструкций, если он имеется, но перед любым другим кодом.</span><span class="sxs-lookup"><span data-stu-id="8950f-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8950f-115">Не следует путать ссылки на проекты с `Imports` инструкции или `Declare` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8950f-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="8950f-116">Ссылки на проекты делают внешние объекты, такие как объекты в сборках, доступные для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] проектов.</span><span class="sxs-lookup"><span data-stu-id="8950f-116">Project references make external objects, such as objects in assemblies, available to [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] projects.</span></span> <span data-ttu-id="8950f-117">`Imports` Инструкция используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам.</span><span class="sxs-lookup"><span data-stu-id="8950f-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="8950f-118">`Declare` Оператор используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="8950f-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="8950f-119">Использование псевдонимов с оператором Imports</span><span class="sxs-lookup"><span data-stu-id="8950f-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="8950f-120">`Imports` Инструкция облегчает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок.</span><span class="sxs-lookup"><span data-stu-id="8950f-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="8950f-121">Псевдонимы позволяют присваивать более понятные имена только на одну часть пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8950f-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="8950f-122">Например, возврат каретки и перевод строки последовательность, которая единый фрагмент текста, который будет отображаться на несколько строк является частью <xref:Microsoft.VisualBasic.ControlChars> модуля в <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8950f-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8950f-123">Для использования этой константы в программе без псевдонима, потребовалось бы введите следующий код:</span><span class="sxs-lookup"><span data-stu-id="8950f-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="8950f-124">`Imports`операторы всегда должны сразу же после первой строки `Option` инструкции в модуле.</span><span class="sxs-lookup"><span data-stu-id="8950f-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="8950f-125">В следующем фрагменте кода показано, как импортировать и присваивать псевдоним <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> модуля:</span><span class="sxs-lookup"><span data-stu-id="8950f-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="8950f-126">Будущие ссылки на это пространство имен может быть значительно более краткими:</span><span class="sxs-lookup"><span data-stu-id="8950f-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="8950f-127">Если `Imports` инструкции псевдоним не включен, элементы, определенные в импортированном пространстве имен, которые могут использоваться в модуле без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="8950f-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="8950f-128">Если указано имя псевдонима, он должен использоваться как квалификатор имен, содержащихся в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8950f-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8950f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8950f-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [<span data-ttu-id="8950f-130">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8950f-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="8950f-131">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="8950f-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="8950f-132">Практическое руководство. Создание и использование сборок с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="8950f-132">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="8950f-133">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="8950f-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
