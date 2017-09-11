---
title: "Структура программы Visual Basic | Документы Microsoft"
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
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
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
ms.openlocfilehash: 3e16ea51d0f766fcb5866cde89e5384a153ac050
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="b024e-102">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b024e-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="b024e-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программа построена из стандартных блоков.</span><span class="sxs-lookup"><span data-stu-id="b024e-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program is built up from standard building blocks.</span></span> <span data-ttu-id="b024e-104">Объект *решение* состоит из одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="b024e-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="b024e-105">Объект *проекта* в свою очередь может содержать одну или несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="b024e-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="b024e-106">Каждый *сборки* компилируется из одного или нескольких исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="b024e-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="b024e-107">Объект *исходный файл* содержит определения и реализации классов, структур, модулей и интерфейсов, которые в конечном счете содержит весь код.</span><span class="sxs-lookup"><span data-stu-id="b024e-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="b024e-108">Дополнительные сведения о таких стандартных блоков [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы см. в разделе [решения и проекты](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) и [сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="b024e-108">For more information about these building blocks of a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program, see [Solutions and Projects](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="b024e-109">Элементы программирования уровня файла</span><span class="sxs-lookup"><span data-stu-id="b024e-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="b024e-110">При запуске проекта или файла и открыть редактор кода, появиться код уже на месте и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="b024e-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="b024e-111">Любой код, написанный следует придерживаться следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="b024e-111">Any code that you write should follow the following sequence:</span></span>  
  
1.  <span data-ttu-id="b024e-112">`Option`инструкции</span><span class="sxs-lookup"><span data-stu-id="b024e-112">`Option` statements</span></span>  
  
2.  <span data-ttu-id="b024e-113">`Imports`инструкции</span><span class="sxs-lookup"><span data-stu-id="b024e-113">`Imports` statements</span></span>  
  
3.  <span data-ttu-id="b024e-114">`Namespace`инструкции и элементы уровня пространства имен</span><span class="sxs-lookup"><span data-stu-id="b024e-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="b024e-115">Введите инструкции в другом порядке, может привести к ошибкам компиляции.</span><span class="sxs-lookup"><span data-stu-id="b024e-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="b024e-116">Программа также может содержать операторы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="b024e-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="b024e-117">Можно смешивать их в исходный файл вместе предыдущей последовательности.</span><span class="sxs-lookup"><span data-stu-id="b024e-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="b024e-118">Параметры инструкции</span><span class="sxs-lookup"><span data-stu-id="b024e-118">Option Statements</span></span>  
 <span data-ttu-id="b024e-119">`Option`Инструкции устанавливают основные правила для последующего кода, способствуя предотвращению синтаксических и логических ошибок.</span><span class="sxs-lookup"><span data-stu-id="b024e-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="b024e-120">[Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) гарантирует, что все переменные объявлены и написаны правильно, что снижает время при отладке.</span><span class="sxs-lookup"><span data-stu-id="b024e-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="b024e-121">[Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) позволяет свести к минимуму логики ошибок и потери данных, возникающих при работе с переменными различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="b024e-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="b024e-122">[Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) указывает способа сравнения строк друг с другом, либо на основе их `Binary` или `Text` значения.</span><span class="sxs-lookup"><span data-stu-id="b024e-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="b024e-123">Оператор Imports</span><span class="sxs-lookup"><span data-stu-id="b024e-123">Imports Statements</span></span>  
 <span data-ttu-id="b024e-124">Можно включить [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Чтобы импортировать имена, определенные вне проекта.</span><span class="sxs-lookup"><span data-stu-id="b024e-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="b024e-125">`Imports` Оператор разрешает код, чтобы ссылаться на классы и другие типы, определенные в импортированном пространстве имен, без их уточнения.</span><span class="sxs-lookup"><span data-stu-id="b024e-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="b024e-126">Можно использовать любое количество `Imports` соответствующих операторов.</span><span class="sxs-lookup"><span data-stu-id="b024e-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="b024e-127">Дополнительные сведения см. в разделе [ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b024e-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="b024e-128">Операторы пространства имен</span><span class="sxs-lookup"><span data-stu-id="b024e-128">Namespace Statements</span></span>  
 <span data-ttu-id="b024e-129">Пространства имен помогают организовать и классифицировать элементы программирования для упрощения группировки и доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="b024e-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="b024e-130">Использовать [оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) для классификации следующих операторов в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="b024e-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="b024e-131">Дополнительные сведения см. в разделе [пространств имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b024e-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="b024e-132">Операторы условной компиляции</span><span class="sxs-lookup"><span data-stu-id="b024e-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="b024e-133">Операторы условной компиляции могут использоваться практически в любом месте в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b024e-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="b024e-134">Они могут вызывать части кода, чтобы включить или исключить во время компиляции в зависимости от определенных условий.</span><span class="sxs-lookup"><span data-stu-id="b024e-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="b024e-135">Также их использовании для отладки приложения, поскольку условный код выполняется только в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="b024e-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="b024e-136">Дополнительные сведения см. в разделе [условной компиляции](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="b024e-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="b024e-137">Элементы программирования уровня пространства имен</span><span class="sxs-lookup"><span data-stu-id="b024e-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="b024e-138">Классы, структуры и модули содержат весь код в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b024e-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="b024e-139">Они являются *уровня пространства имен* элементов, которые могут находиться в пространстве имен или на уровне исходного файла.</span><span class="sxs-lookup"><span data-stu-id="b024e-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="b024e-140">Они содержат описания всех других элементов программирования.</span><span class="sxs-lookup"><span data-stu-id="b024e-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="b024e-141">Интерфейсы, которые определяют подписи элементов, но не выполняют реализацию, также отображаются на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="b024e-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="b024e-142">Дополнительные сведения об элементах уровня модуля см.</span><span class="sxs-lookup"><span data-stu-id="b024e-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="b024e-143">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="b024e-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="b024e-144">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="b024e-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="b024e-145">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="b024e-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="b024e-146">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="b024e-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="b024e-147">Элементы данных на уровне пространства имен, перечисления и делегаты.</span><span class="sxs-lookup"><span data-stu-id="b024e-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="b024e-148">Элементы программирования уровня модуля</span><span class="sxs-lookup"><span data-stu-id="b024e-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="b024e-149">Процедуры, операторы, свойства и события являются единственными элементами программирования, которые могут содержать исполняемый код (инструкции, которые выполняют действия во время выполнения).</span><span class="sxs-lookup"><span data-stu-id="b024e-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="b024e-150">Они являются *уровня модуля* элементы программы.</span><span class="sxs-lookup"><span data-stu-id="b024e-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="b024e-151">Дополнительные сведения об элементах уровня процедуры см.</span><span class="sxs-lookup"><span data-stu-id="b024e-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="b024e-152">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="b024e-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="b024e-153">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="b024e-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="b024e-154">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="b024e-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="b024e-155">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="b024e-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="b024e-156">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="b024e-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="b024e-157">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="b024e-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="b024e-158">Элементы данных на уровне модуля являются переменные, константы, перечисления и делегаты.</span><span class="sxs-lookup"><span data-stu-id="b024e-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="b024e-159">Элементы программирования уровня процедуры</span><span class="sxs-lookup"><span data-stu-id="b024e-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="b024e-160">Большая часть содержимого *уровня процедуры* элементы, исполняемые операторы, которые составляют код времени выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="b024e-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="b024e-161">Весь исполняемый код должен быть в какой-либо процедуры (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span><span class="sxs-lookup"><span data-stu-id="b024e-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="b024e-162">Дополнительные сведения см. в разделе [инструкции](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="b024e-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="b024e-163">Элементы данных на уровне процедуры ограничиваются локальные переменные и константы.</span><span class="sxs-lookup"><span data-stu-id="b024e-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="b024e-164">Основная процедура</span><span class="sxs-lookup"><span data-stu-id="b024e-164">The Main Procedure</span></span>  
 <span data-ttu-id="b024e-165">`Main` Процедура — это первый код для запуска при загрузке приложения.</span><span class="sxs-lookup"><span data-stu-id="b024e-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="b024e-166">`Main`служит в качестве начальной точки и общего управления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b024e-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="b024e-167">Существует четыре вида `Main`:</span><span class="sxs-lookup"><span data-stu-id="b024e-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="b024e-168">Наиболее распространенный вид данной процедуры — `Sub Main()`.</span><span class="sxs-lookup"><span data-stu-id="b024e-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="b024e-169">Дополнительные сведения см. в разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="b024e-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b024e-170">См. также</span><span class="sxs-lookup"><span data-stu-id="b024e-170">See Also</span></span>  
 <span data-ttu-id="b024e-171">[Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="b024e-171">[Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span></span>  
<span data-ttu-id="b024e-172"> [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="b024e-172"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="b024e-173"> [Ограничения в Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)</span><span class="sxs-lookup"><span data-stu-id="b024e-173"> [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)</span></span>
