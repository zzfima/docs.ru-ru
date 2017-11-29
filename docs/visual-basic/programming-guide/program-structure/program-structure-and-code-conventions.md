---
title: "Соглашения о структуре программы и коде (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b38ba9623a20dcd1be4bc96f4aff1eb646b0a053
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="3bd32-102">Соглашения о структуре программы и коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bd32-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="3bd32-103">В этом разделе представлены типичная [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] структура программы, простая [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программа «Hello, World», а также обсуждаются [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] соглашения о коде.</span><span class="sxs-lookup"><span data-stu-id="3bd32-103">This section introduces the typical [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program structure, provides a simple [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code conventions.</span></span> <span data-ttu-id="3bd32-104">Соглашения о написании кода, рекомендации, которые касаются не на логику программы, а также на ее физическую структуру и внешний вид.</span><span class="sxs-lookup"><span data-stu-id="3bd32-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="3bd32-105">После их делает код проще читать, понимать и поддерживать.</span><span class="sxs-lookup"><span data-stu-id="3bd32-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="3bd32-106">Соглашения о коде могут включать среди прочего:</span><span class="sxs-lookup"><span data-stu-id="3bd32-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="3bd32-107">Стандартизованные форматы меток и комментирования кода.</span><span class="sxs-lookup"><span data-stu-id="3bd32-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="3bd32-108">Рекомендации для интервала, форматирования и создания отступов кода.</span><span class="sxs-lookup"><span data-stu-id="3bd32-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="3bd32-109">Соглашения об именовании объектов, переменных и процедур.</span><span class="sxs-lookup"><span data-stu-id="3bd32-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="3bd32-110">Ниже содержится ряд рекомендации по программированию [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы, а также примеры применения.</span><span class="sxs-lookup"><span data-stu-id="3bd32-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bd32-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="3bd32-111">In This Section</span></span>  
 [<span data-ttu-id="3bd32-112">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bd32-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="3bd32-113">Общие сведения о составляющих элементов [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="3bd32-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="3bd32-114">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bd32-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="3bd32-115">Описывает процедуру, которая служит в качестве начальной точки и общего управления для приложения.</span><span class="sxs-lookup"><span data-stu-id="3bd32-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="3bd32-116">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="3bd32-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="3bd32-117">Описывает, как ссылаться на объекты в других сборках.</span><span class="sxs-lookup"><span data-stu-id="3bd32-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="3bd32-118">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bd32-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="3bd32-119">Описывает, как пространства имен упорядочивания объектов в сборках.</span><span class="sxs-lookup"><span data-stu-id="3bd32-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="3bd32-120">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bd32-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="3bd32-121">Содержит общие рекомендации по именованию процедур, константы, переменные, аргументы и объекты.</span><span class="sxs-lookup"><span data-stu-id="3bd32-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="3bd32-122">Соглашения о написании кода Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bd32-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="3bd32-123">Общие сведения о правилах, используемых при разработке примеров в данной документации.</span><span class="sxs-lookup"><span data-stu-id="3bd32-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="3bd32-124">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="3bd32-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="3bd32-125">Описывает, как выборочно скомпилировать одни блоки кода, игнорировать другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="3bd32-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="3bd32-126">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="3bd32-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="3bd32-127">Показано, как разделить длинных операторов на несколько строк и сбора коротких операторов в одну строку.</span><span class="sxs-lookup"><span data-stu-id="3bd32-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="3bd32-128">Практическое руководство. Сворачивание и скрытие частей кода</span><span class="sxs-lookup"><span data-stu-id="3bd32-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="3bd32-129">Показано, как Сворачивание и скрытие частей кода в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] редактора кода.</span><span class="sxs-lookup"><span data-stu-id="3bd32-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="3bd32-130">Практическое руководство. Операторы меток</span><span class="sxs-lookup"><span data-stu-id="3bd32-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="3bd32-131">Показано, как пометить строку кода для обозначения при использовании операторами, такие как `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="3bd32-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="3bd32-132">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="3bd32-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="3bd32-133">Показано, как и где использовать нецифровые и неалфавитные символы.</span><span class="sxs-lookup"><span data-stu-id="3bd32-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="3bd32-134">Комментарии в коде</span><span class="sxs-lookup"><span data-stu-id="3bd32-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="3bd32-135">Описывает добавление описательные комментарии в коде.</span><span class="sxs-lookup"><span data-stu-id="3bd32-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="3bd32-136">Ключевые слова как имена элементов в коде</span><span class="sxs-lookup"><span data-stu-id="3bd32-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="3bd32-137">Описывает использование квадратных скобок (`[]`) для обозначения имен переменных, которые также [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="3bd32-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="3bd32-138">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="3bd32-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="3bd32-139">Описывает различные способы обращения к элементам [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="3bd32-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="3bd32-140">Ограничения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bd32-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="3bd32-141">Описание устранения известных ограничений кода в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bd32-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3bd32-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3bd32-142">Related Sections</span></span>  
 [<span data-ttu-id="3bd32-143">Условные обозначения и соглашения о коде</span><span class="sxs-lookup"><span data-stu-id="3bd32-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="3bd32-144">Предоставляет стандартные соглашения о написании кода для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bd32-144">Provides standard coding conventions for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="3bd32-145">Создание кода</span><span class="sxs-lookup"><span data-stu-id="3bd32-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="3bd32-146">Описание возможностей, облегчающих написание и управление им код.</span><span class="sxs-lookup"><span data-stu-id="3bd32-146">Describes features that make it easier for you to write and manage your code.</span></span>
