---
title: Условная компиляция в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967858"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="6fa86-102">Условная компиляция в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fa86-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="6fa86-103">В *условной компиляции*, одни блоки кода в программе компилируются, а остальные игнорируются.</span><span class="sxs-lookup"><span data-stu-id="6fa86-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="6fa86-104">Например, может потребоваться написать инструкций отладки, которые сравнивают скорость различные подходы к той же задачи программирования, или может потребоваться локализации приложения для нескольких языков.</span><span class="sxs-lookup"><span data-stu-id="6fa86-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="6fa86-105">Условная компиляция инструкции предназначены для выполнения во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6fa86-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="6fa86-106">Блоки кода для условной компиляции с `#If...Then...#Else` директива.</span><span class="sxs-lookup"><span data-stu-id="6fa86-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="6fa86-107">Например, для создания на французском и немецком языках версии того же приложения с использованием того же исходного кода, необходимо внедрить сегменты кода платформы в `#If...Then` инструкции с помощью предопределенных констант `FrenchVersion` и `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="6fa86-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="6fa86-108">В следующем примере показано, как:</span><span class="sxs-lookup"><span data-stu-id="6fa86-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="6fa86-109">Если вы установите для параметра `FrenchVersion` для константы условной компиляции `True` во время компиляции, компилируется условный код для французской версии.</span><span class="sxs-lookup"><span data-stu-id="6fa86-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="6fa86-110">Если вы установите для параметра `GermanVersion` константа, которая `True`, компилятор использует версия для немецкого языка.</span><span class="sxs-lookup"><span data-stu-id="6fa86-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="6fa86-111">Если ни один равно `True`, код в последнем `Else` блоке.</span><span class="sxs-lookup"><span data-stu-id="6fa86-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fa86-112">Автозавершение будут не работает при редактировании кода и с помощью директив условной компиляции, если код не является частью текущей ветви.</span><span class="sxs-lookup"><span data-stu-id="6fa86-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="6fa86-113">Объявление констант условной компиляции</span><span class="sxs-lookup"><span data-stu-id="6fa86-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="6fa86-114">Константы условной компиляции можно задать одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="6fa86-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
-   <span data-ttu-id="6fa86-115">В **в конструкторе проектов**</span><span class="sxs-lookup"><span data-stu-id="6fa86-115">In the **Project Designer**</span></span>  
  
-   <span data-ttu-id="6fa86-116">В командной строке при использовании компилятора командной строки</span><span class="sxs-lookup"><span data-stu-id="6fa86-116">At the command line when using the command-line compiler</span></span>  
  
-   <span data-ttu-id="6fa86-117">В коде</span><span class="sxs-lookup"><span data-stu-id="6fa86-117">In your code</span></span>  
  
 <span data-ttu-id="6fa86-118">Константы условной компиляции находятся в отдельной области и недоступны из обычного кода.</span><span class="sxs-lookup"><span data-stu-id="6fa86-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="6fa86-119">Область константы условной компиляции, зависит от того, который имеет значение.</span><span class="sxs-lookup"><span data-stu-id="6fa86-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="6fa86-120">Ниже перечислены области константы, объявленные с помощью каждого из трех описанных выше методов.</span><span class="sxs-lookup"><span data-stu-id="6fa86-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="6fa86-121">Способ задания константы</span><span class="sxs-lookup"><span data-stu-id="6fa86-121">How constant is set</span></span>|<span data-ttu-id="6fa86-122">Область действия констант</span><span class="sxs-lookup"><span data-stu-id="6fa86-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="6fa86-123">**Конструктор проектов**</span><span class="sxs-lookup"><span data-stu-id="6fa86-123">**Project Designer**</span></span>|<span data-ttu-id="6fa86-124">Открыта для всех файлов в проекте</span><span class="sxs-lookup"><span data-stu-id="6fa86-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="6fa86-125">Командная строка</span><span class="sxs-lookup"><span data-stu-id="6fa86-125">Command line</span></span>|<span data-ttu-id="6fa86-126">Открыта для всех файлов, передаваемые компилятору командной строки</span><span class="sxs-lookup"><span data-stu-id="6fa86-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="6fa86-127">`#Const` в коде</span><span class="sxs-lookup"><span data-stu-id="6fa86-127">`#Const` statement in code</span></span>|<span data-ttu-id="6fa86-128">Внутри файла, в котором она объявлена</span><span class="sxs-lookup"><span data-stu-id="6fa86-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="6fa86-129">Чтобы задать константы в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="6fa86-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="6fa86-130">-Прежде чем создавать исполняемый файл, задайте константы **конструктор проектов** , выполнив действия, описанные в [управление проектом и свойства решения](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="6fa86-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="6fa86-131">Чтобы задать константы из командной строки</span><span class="sxs-lookup"><span data-stu-id="6fa86-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="6fa86-132">— Используйте **/d** вставьте константы условной компиляции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6fa86-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="6fa86-133">Без пробела между **/d** коммутатора и первая константа.</span><span class="sxs-lookup"><span data-stu-id="6fa86-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="6fa86-134">Дополнительные сведения см. в разделе [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="6fa86-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="6fa86-135">Объявления из командной строки переопределяют объявления в **конструктор проектов**, но не удаляют их.</span><span class="sxs-lookup"><span data-stu-id="6fa86-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="6fa86-136">Задать аргументы в **конструктор проектов** остаются в силе для последующих компиляциях.</span><span class="sxs-lookup"><span data-stu-id="6fa86-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="6fa86-137">При написании константы в коде, не существует strict правил по их расположению, однако их область действия всего модуля, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="6fa86-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="6fa86-138">Чтобы задать константы в коде</span><span class="sxs-lookup"><span data-stu-id="6fa86-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="6fa86-139">-Установите константы в блоке объявления модуля, в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="6fa86-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="6fa86-140">Это позволяет сохранить код и облегчить для чтения.</span><span class="sxs-lookup"><span data-stu-id="6fa86-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="6fa86-141">См. также</span><span class="sxs-lookup"><span data-stu-id="6fa86-141">Related Topics</span></span>  
  
|<span data-ttu-id="6fa86-142">Заголовок</span><span class="sxs-lookup"><span data-stu-id="6fa86-142">Title</span></span>|<span data-ttu-id="6fa86-143">Описание:</span><span class="sxs-lookup"><span data-stu-id="6fa86-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="6fa86-144">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="6fa86-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="6fa86-145">Рекомендации по упрощению чтение и обслуживание кода.</span><span class="sxs-lookup"><span data-stu-id="6fa86-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="6fa86-146">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6fa86-146">Reference</span></span>  
 [<span data-ttu-id="6fa86-147">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="6fa86-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="6fa86-148">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="6fa86-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="6fa86-149">/ define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fa86-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
