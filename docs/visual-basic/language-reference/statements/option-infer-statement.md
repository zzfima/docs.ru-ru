---
title: "Option Infer - оператор"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a><span data-ttu-id="5c4c3-102">Option Infer - оператор</span><span class="sxs-lookup"><span data-stu-id="5c4c3-102">Option Infer Statement</span></span>
<span data-ttu-id="5c4c3-103">Включает использование локального определения типов при объявлении переменных.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c4c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c4c3-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="5c4c3-105">Части</span><span class="sxs-lookup"><span data-stu-id="5c4c3-105">Parts</span></span>  
  
|<span data-ttu-id="5c4c3-106">Термин</span><span class="sxs-lookup"><span data-stu-id="5c4c3-106">Term</span></span>|<span data-ttu-id="5c4c3-107">Определение</span><span class="sxs-lookup"><span data-stu-id="5c4c3-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="5c4c3-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-108">Optional.</span></span> <span data-ttu-id="5c4c3-109">Включает локальное определение типов.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="5c4c3-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-110">Optional.</span></span> <span data-ttu-id="5c4c3-111">Отключает локальное определение типов.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c4c3-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c4c3-112">Remarks</span></span>  
 <span data-ttu-id="5c4c3-113">Чтобы задать `Option Infer` в файле, введите `Option Infer On` или `Option Infer Off` в начале файла перед всем остальным исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="5c4c3-114">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="5c4c3-115">Если задать для `Option Infer` значение `On`, можно объявлять локальные переменные, не задавая явным образом тип данных.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="5c4c3-116">Компилятор определяет тип переменной по типу ее выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="5c4c3-117">На следующей иллюстрации `Option Infer` включен.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="5c4c3-118">Переменная в объявлении `Dim someVar = 2` объявляется как целочисленная определением типов.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="5c4c3-119">![IntelliSense-просмотров объявления. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="5c4c3-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="5c4c3-120">IntelliSense при включенном параметре Option Infer</span><span class="sxs-lookup"><span data-stu-id="5c4c3-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="5c4c3-121">На следующей иллюстрации `Option Infer` отключен.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="5c4c3-122">Переменная в объявлении `Dim someVar = 2` объявляется как `Object` определением типов.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="5c4c3-123">В этом примере **Option Strict** принимает значение **Off** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5c4c3-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="5c4c3-124">![IntelliSense-просмотров объявления. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="5c4c3-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="5c4c3-125">IntelliSense при отключенном параметре Option Infer</span><span class="sxs-lookup"><span data-stu-id="5c4c3-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c4c3-126">Если переменная объявлена как `Object`, тип времени выполнения может измениться в ходе работы программы.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5c4c3-127">выполняет операции *упаковка-преобразование* и *распаковки* для преобразования между `Object` и тип значения, что замедляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-127"> performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="5c4c3-128">Сведения об упаковке и распаковке см. в разделе [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c3-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="5c4c3-129">Определение типов применяется на уровне процедур и не применяется вне процедур в классах, структурах, модулях и интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="5c4c3-130">Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c3-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="5c4c3-131">Если оператор Option Infer отсутствует</span><span class="sxs-lookup"><span data-stu-id="5c4c3-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="5c4c3-132">Если исходный код не содержит `Option Infer` инструкции **Option Infer** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="5c4c3-133">При использовании компилятора командной строки [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="5c4c3-134">Чтобы включить Option Infer в среде разработки</span><span class="sxs-lookup"><span data-stu-id="5c4c3-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="5c4c3-135">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="5c4c3-136">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-136">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="5c4c3-137">Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="5c4c3-137">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="5c4c3-138">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-138">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="5c4c3-139">Задайте значение в **Option infer** поле.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-139">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="5c4c3-140">При создании нового проекта **Option Infer** на **компиляции** набор вкладок **Option Infer** в **VB по умолчанию** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="5c4c3-141">Чтобы получить доступ к **VB по умолчанию** в диалоговом **средства** меню, нажмите кнопку **параметры**.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="5c4c3-142">В **параметры** диалогового окна разверните **проекты и решения**, а затем нажмите кнопку **VB по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="5c4c3-143">Начальный параметр по умолчанию в **VB значения по умолчанию** — `On`.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-143">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="5c4c3-144">Чтобы включить Option Infer в командной строке</span><span class="sxs-lookup"><span data-stu-id="5c4c3-144">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="5c4c3-145">Включить [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) параметра компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-145">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="5c4c3-146">Типы данных и значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5c4c3-146">Default Data Types and Values</span></span>  
 <span data-ttu-id="5c4c3-147">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="5c4c3-148">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="5c4c3-148">Data type specified?</span></span>|<span data-ttu-id="5c4c3-149">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="5c4c3-149">Initializer specified?</span></span>|<span data-ttu-id="5c4c3-150">Пример</span><span class="sxs-lookup"><span data-stu-id="5c4c3-150">Example</span></span>|<span data-ttu-id="5c4c3-151">Результат</span><span class="sxs-lookup"><span data-stu-id="5c4c3-151">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="5c4c3-152">Нет</span><span class="sxs-lookup"><span data-stu-id="5c4c3-152">No</span></span>|<span data-ttu-id="5c4c3-153">Нет</span><span class="sxs-lookup"><span data-stu-id="5c4c3-153">No</span></span>|`Dim qty`|<span data-ttu-id="5c4c3-154">Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="5c4c3-155">Если параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="5c4c3-156">Нет</span><span class="sxs-lookup"><span data-stu-id="5c4c3-156">No</span></span>|<span data-ttu-id="5c4c3-157">Да</span><span class="sxs-lookup"><span data-stu-id="5c4c3-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="5c4c3-158">Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="5c4c3-159">В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c3-159">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="5c4c3-160">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="5c4c3-161">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="5c4c3-162">Да</span><span class="sxs-lookup"><span data-stu-id="5c4c3-162">Yes</span></span>|<span data-ttu-id="5c4c3-163">Нет</span><span class="sxs-lookup"><span data-stu-id="5c4c3-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="5c4c3-164">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="5c4c3-165">Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c3-165">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="5c4c3-166">Да</span><span class="sxs-lookup"><span data-stu-id="5c4c3-166">Yes</span></span>|<span data-ttu-id="5c4c3-167">Да</span><span class="sxs-lookup"><span data-stu-id="5c4c3-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="5c4c3-168">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c4c3-169">Пример</span><span class="sxs-lookup"><span data-stu-id="5c4c3-169">Example</span></span>  
 <span data-ttu-id="5c4c3-170">В следующих примерах показано, как оператор `Option Infer` включает локальное определение типов.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5c4c3-171">Пример</span><span class="sxs-lookup"><span data-stu-id="5c4c3-171">Example</span></span>  
 <span data-ttu-id="5c4c3-172">В следующем примере показано, что тип времени выполнения может различаться, когда переменная указана как `Object`.</span><span class="sxs-lookup"><span data-stu-id="5c4c3-172">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5c4c3-173">См. также</span><span class="sxs-lookup"><span data-stu-id="5c4c3-173">See Also</span></span>  
 [<span data-ttu-id="5c4c3-174">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="5c4c3-174">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="5c4c3-175">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="5c4c3-175">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="5c4c3-176">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="5c4c3-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="5c4c3-177">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="5c4c3-177">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="5c4c3-178">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="5c4c3-178">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="5c4c3-179">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="5c4c3-179">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="5c4c3-180">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="5c4c3-180">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="5c4c3-181">Упаковка-преобразование и распаковка-преобразование</span><span class="sxs-lookup"><span data-stu-id="5c4c3-181">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
