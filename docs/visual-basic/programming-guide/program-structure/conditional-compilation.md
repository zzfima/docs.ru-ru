---
title: Условная компиляция
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 19a2c70941a9a72574f7e624743def74b80c4e39
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347462"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="201f8-102">Условная компиляция в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="201f8-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="201f8-103">В *условной компиляции*определенные блоки кода в программе компилируются выборочно, а другие игнорируются.</span><span class="sxs-lookup"><span data-stu-id="201f8-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="201f8-104">Например, может потребоваться написать инструкции отладки, которые сравнивают скорость различных подходов к одной задаче программирования, или вы можете локализовать приложение для нескольких языков.</span><span class="sxs-lookup"><span data-stu-id="201f8-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="201f8-105">Операторы условной компиляции предназначены для запуска во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="201f8-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="201f8-106">Вы запишите блоки кода для условной компиляции с помощью директивы `#If...Then...#Else`.</span><span class="sxs-lookup"><span data-stu-id="201f8-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="201f8-107">Например, для создания версий одного и того же приложения на французском и немецком языках из одного и того же исходного кода необходимо внедрить сегменты кода, зависящие от платформы, в `#If...Then` операторы, используя предопределенные константы `FrenchVersion` и `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="201f8-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="201f8-108">В следующем примере показано, как:</span><span class="sxs-lookup"><span data-stu-id="201f8-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="201f8-109">Если задать значение константы условной компиляции `FrenchVersion` для `True` во время компиляции, компилируется условный код для французской версии.</span><span class="sxs-lookup"><span data-stu-id="201f8-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="201f8-110">Если для константы `GermanVersion` задано значение `True`, компилятор использует немецкую версию.</span><span class="sxs-lookup"><span data-stu-id="201f8-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="201f8-111">Если ни один из них не имеет значение `True`, выполняется код в последнем блоке `Else`.</span><span class="sxs-lookup"><span data-stu-id="201f8-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="201f8-112">Автозаполнение не будет работать при редактировании кода и использовании директив условной компиляции, если код не является частью текущей ветви.</span><span class="sxs-lookup"><span data-stu-id="201f8-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="201f8-113">Объявление констант условной компиляции</span><span class="sxs-lookup"><span data-stu-id="201f8-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="201f8-114">Константы условной компиляции можно задать одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="201f8-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="201f8-115">В **конструкторе проектов**</span><span class="sxs-lookup"><span data-stu-id="201f8-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="201f8-116">В командной строке при использовании компилятора командной строки</span><span class="sxs-lookup"><span data-stu-id="201f8-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="201f8-117">В коде</span><span class="sxs-lookup"><span data-stu-id="201f8-117">In your code</span></span>  
  
 <span data-ttu-id="201f8-118">Константы условной компиляции имеют специальную область и недоступны из стандартного кода.</span><span class="sxs-lookup"><span data-stu-id="201f8-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="201f8-119">Область константы условной компиляции зависит от того, как она задана.</span><span class="sxs-lookup"><span data-stu-id="201f8-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="201f8-120">В следующей таблице перечислены области констант, объявленных с помощью каждого из трех описанных выше способов.</span><span class="sxs-lookup"><span data-stu-id="201f8-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="201f8-121">Как задается константа</span><span class="sxs-lookup"><span data-stu-id="201f8-121">How constant is set</span></span>|<span data-ttu-id="201f8-122">Область действия константы</span><span class="sxs-lookup"><span data-stu-id="201f8-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="201f8-123">**Конструктор проектов**</span><span class="sxs-lookup"><span data-stu-id="201f8-123">**Project Designer**</span></span>|<span data-ttu-id="201f8-124">Открыт для всех файлов в проекте</span><span class="sxs-lookup"><span data-stu-id="201f8-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="201f8-125">Командная строка</span><span class="sxs-lookup"><span data-stu-id="201f8-125">Command line</span></span>|<span data-ttu-id="201f8-126">Открытый для всех файлов, переданных компилятору командной строки</span><span class="sxs-lookup"><span data-stu-id="201f8-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="201f8-127">`#Const`ная инструкция в коде</span><span class="sxs-lookup"><span data-stu-id="201f8-127">`#Const` statement in code</span></span>|<span data-ttu-id="201f8-128">Закрытый для файла, в котором он объявлен</span><span class="sxs-lookup"><span data-stu-id="201f8-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="201f8-129">Задание констант в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="201f8-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="201f8-130">— Перед созданием исполняемого файла задайте константы в **конструкторе проектов** , выполнив действия, описанные в разделе [Управление свойствами проекта и решения](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="201f8-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="201f8-131">Задание констант в командной строке</span><span class="sxs-lookup"><span data-stu-id="201f8-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="201f8-132">— Используйте параметр **-d** , чтобы ввести константы условной компиляции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="201f8-132">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="201f8-133">Между параметром **-d** и первой константой не должно быть пробелов.</span><span class="sxs-lookup"><span data-stu-id="201f8-133">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="201f8-134">Дополнительные сведения см. в разделе [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="201f8-134">For more information, see [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="201f8-135">Объявления из командной строки переопределяют объявления, указанные в **конструкторе проектов**, но не удаляют их.</span><span class="sxs-lookup"><span data-stu-id="201f8-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="201f8-136">Аргументы, заданные в **конструкторе проектов** , действуют для последующих компиляций.</span><span class="sxs-lookup"><span data-stu-id="201f8-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="201f8-137">При написании констант в самом коде нет никаких правил для их размещения, поскольку их областью действия является весь модуль, в котором они объявляются.</span><span class="sxs-lookup"><span data-stu-id="201f8-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="201f8-138">Задание констант в коде</span><span class="sxs-lookup"><span data-stu-id="201f8-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="201f8-139">-Поместите константы в блок объявления модуля, в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="201f8-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="201f8-140">Это помогает организовать структурирование кода и облегчить его чтение.</span><span class="sxs-lookup"><span data-stu-id="201f8-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="201f8-141">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="201f8-141">Related Topics</span></span>  
  
|<span data-ttu-id="201f8-142">Название</span><span class="sxs-lookup"><span data-stu-id="201f8-142">Title</span></span>|<span data-ttu-id="201f8-143">Описание</span><span class="sxs-lookup"><span data-stu-id="201f8-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="201f8-144">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="201f8-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="201f8-145">Предоставляет рекомендации по упрощению чтения и сопровождения кода.</span><span class="sxs-lookup"><span data-stu-id="201f8-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="201f8-146">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="201f8-146">Reference</span></span>  
 [<span data-ttu-id="201f8-147">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="201f8-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="201f8-148">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="201f8-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="201f8-149">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="201f8-149">-define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
