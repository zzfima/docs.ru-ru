---
title: "Условная компиляция в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 559380dc9baceb2fba4dca782e83f335f1bcd92d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="94831-102">Условная компиляция в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94831-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="94831-103">В *условной компиляции*, определенной блоки кода в программе компилируются, пока другие атрибуты игнорируются.</span><span class="sxs-lookup"><span data-stu-id="94831-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="94831-104">Например, может потребоваться написать инструкций отладки, которые сравнивают скорость различные подходы к той же задачи программирования, или может потребоваться локализации приложения для нескольких языков.</span><span class="sxs-lookup"><span data-stu-id="94831-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="94831-105">Условная компиляция инструкции предназначены для выполнения во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="94831-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="94831-106">Блоки кода для условной компиляции с `#If...Then...#Else` директивы.</span><span class="sxs-lookup"><span data-stu-id="94831-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="94831-107">Например, для создания французском и немецком языках версии одного приложения из того же исходного кода, необходимо внедрить сегменты кода для конкретной платформы в `#If...Then` операторов с использованием предопределенных констант `FrenchVersion` и `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="94831-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="94831-108">В следующем примере показано, как:</span><span class="sxs-lookup"><span data-stu-id="94831-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 <span data-ttu-id="94831-109">Если задать значение `FrenchVersion` для константы условной компиляции `True` во время компиляции, компилируется условный код для французской версии.</span><span class="sxs-lookup"><span data-stu-id="94831-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="94831-110">Если задать значение `GermanVersion` константа, которая `True`, компилятор использует немецкую версию.</span><span class="sxs-lookup"><span data-stu-id="94831-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="94831-111">Если не задан ни один `True`, код в последнем `Else` блок.</span><span class="sxs-lookup"><span data-stu-id="94831-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94831-112">Автоматическое завершение будет не работает при редактировании кода и использовании директив условной компиляции, если код не является частью текущей ветви.</span><span class="sxs-lookup"><span data-stu-id="94831-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="94831-113">Объявление константы условной компиляции</span><span class="sxs-lookup"><span data-stu-id="94831-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="94831-114">Константы условной компиляции можно задать одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="94831-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
-   <span data-ttu-id="94831-115">В **в конструкторе проектов**</span><span class="sxs-lookup"><span data-stu-id="94831-115">In the **Project Designer**</span></span>  
  
-   <span data-ttu-id="94831-116">В командной строке при использовании компилятора командной строки</span><span class="sxs-lookup"><span data-stu-id="94831-116">At the command line when using the command-line compiler</span></span>  
  
-   <span data-ttu-id="94831-117">В коде</span><span class="sxs-lookup"><span data-stu-id="94831-117">In your code</span></span>  
  
 <span data-ttu-id="94831-118">Константы условной компиляции находятся в отдельной области и не доступен из обычного кода.</span><span class="sxs-lookup"><span data-stu-id="94831-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="94831-119">Константа условной компиляции относится зависит от способа его задания.</span><span class="sxs-lookup"><span data-stu-id="94831-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="94831-120">В следующей таблице перечислены области константы, объявленные с помощью каждого из трех описанных выше методов.</span><span class="sxs-lookup"><span data-stu-id="94831-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="94831-121">Способ задания константы</span><span class="sxs-lookup"><span data-stu-id="94831-121">How constant is set</span></span>|<span data-ttu-id="94831-122">Область действия констант</span><span class="sxs-lookup"><span data-stu-id="94831-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="94831-123">**Конструктор проектов**</span><span class="sxs-lookup"><span data-stu-id="94831-123">**Project Designer**</span></span>|<span data-ttu-id="94831-124">Открыта для всех файлов в проекте</span><span class="sxs-lookup"><span data-stu-id="94831-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="94831-125">Командная строка</span><span class="sxs-lookup"><span data-stu-id="94831-125">Command line</span></span>|<span data-ttu-id="94831-126">Открыта для всех файлов, передаваемые компилятору командной строки</span><span class="sxs-lookup"><span data-stu-id="94831-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="94831-127">`#Const`инструкции в коде</span><span class="sxs-lookup"><span data-stu-id="94831-127">`#Const` statement in code</span></span>|<span data-ttu-id="94831-128">Внутри файла, в котором она объявлена</span><span class="sxs-lookup"><span data-stu-id="94831-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="94831-129">Для задания констант в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="94831-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="94831-130">-Перед созданием исполняемого файла, задайте константы **конструктора проектов** , выполнив действия, описанные в [управление проектом и свойства решения](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="94831-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="94831-131">Для задания констант в командной строке</span><span class="sxs-lookup"><span data-stu-id="94831-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="94831-132">-Используйте **/d** вставьте константы условной компиляции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="94831-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="94831-133">Без пробела между **/d** коммутатор и что первая константа.</span><span class="sxs-lookup"><span data-stu-id="94831-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="94831-134">Дополнительные сведения см. в разделе [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="94831-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="94831-135">Объявления из командной строки переопределяют объявления в **конструктора проектов**, но не удаляют их.</span><span class="sxs-lookup"><span data-stu-id="94831-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="94831-136">Задайте аргументы в **конструктора проектов** остаются в силе для последующих компиляциях.</span><span class="sxs-lookup"><span data-stu-id="94831-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="94831-137">При написании константы в коде, нет строгого правил по их расположению, однако их область действия всего модуля, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="94831-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="94831-138">Для задания констант в коде</span><span class="sxs-lookup"><span data-stu-id="94831-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="94831-139">-Установите константы в блоке объявления модуля, в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="94831-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="94831-140">Это помогает поддерживать код и облегчить чтение.</span><span class="sxs-lookup"><span data-stu-id="94831-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="94831-141">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="94831-141">Related Topics</span></span>  
  
|<span data-ttu-id="94831-142">Заголовок</span><span class="sxs-lookup"><span data-stu-id="94831-142">Title</span></span>|<span data-ttu-id="94831-143">Описание</span><span class="sxs-lookup"><span data-stu-id="94831-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="94831-144">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="94831-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="94831-145">Рекомендации по упрощению чтение и обслуживание кода.</span><span class="sxs-lookup"><span data-stu-id="94831-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="94831-146">Ссылка</span><span class="sxs-lookup"><span data-stu-id="94831-146">Reference</span></span>  
 [<span data-ttu-id="94831-147">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="94831-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="94831-148">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="94831-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="94831-149">/ define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94831-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
