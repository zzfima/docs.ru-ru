---
title: Option Infer Statement (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 38c60245ff2c0b08ee731da6c1f88c30e1af8e3f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965831"
---
# <a name="option-infer-statement"></a><span data-ttu-id="7ab93-102">Option Infer - оператор</span><span class="sxs-lookup"><span data-stu-id="7ab93-102">Option Infer Statement</span></span>
<span data-ttu-id="7ab93-103">Включает использование локального определения типов при объявлении переменных.</span><span class="sxs-lookup"><span data-stu-id="7ab93-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ab93-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="7ab93-105">Части</span><span class="sxs-lookup"><span data-stu-id="7ab93-105">Parts</span></span>  
  
|<span data-ttu-id="7ab93-106">Термин</span><span class="sxs-lookup"><span data-stu-id="7ab93-106">Term</span></span>|<span data-ttu-id="7ab93-107">Определение</span><span class="sxs-lookup"><span data-stu-id="7ab93-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="7ab93-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7ab93-108">Optional.</span></span> <span data-ttu-id="7ab93-109">Включает локальное определение типов.</span><span class="sxs-lookup"><span data-stu-id="7ab93-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="7ab93-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7ab93-110">Optional.</span></span> <span data-ttu-id="7ab93-111">Отключает локальное определение типов.</span><span class="sxs-lookup"><span data-stu-id="7ab93-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ab93-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ab93-112">Remarks</span></span>  
 <span data-ttu-id="7ab93-113">Чтобы задать `Option Infer` в файле, введите `Option Infer On` или `Option Infer Off` в начале файла перед всем остальным исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="7ab93-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="7ab93-114">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="7ab93-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="7ab93-115">Если задать для `Option Infer` значение `On`, можно объявлять локальные переменные, не задавая явным образом тип данных.</span><span class="sxs-lookup"><span data-stu-id="7ab93-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="7ab93-116">Компилятор определяет тип переменной по типу ее выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="7ab93-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="7ab93-117">На следующей иллюстрации `Option Infer` включен.</span><span class="sxs-lookup"><span data-stu-id="7ab93-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="7ab93-118">Переменная в объявлении `Dim someVar = 2` объявляется как целочисленная определением типов.</span><span class="sxs-lookup"><span data-stu-id="7ab93-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="7ab93-119">![IntelliSense-просмотров объявления. ](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="7ab93-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="7ab93-120">IntelliSense при включенном параметре Option Infer</span><span class="sxs-lookup"><span data-stu-id="7ab93-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="7ab93-121">На следующей иллюстрации `Option Infer` отключен.</span><span class="sxs-lookup"><span data-stu-id="7ab93-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="7ab93-122">Переменная в объявлении `Dim someVar = 2` объявляется как `Object` определением типов.</span><span class="sxs-lookup"><span data-stu-id="7ab93-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="7ab93-123">В этом примере **Option Strict** установлено значение **Off** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7ab93-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="7ab93-124">![IntelliSense-просмотров объявления. ](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="7ab93-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="7ab93-125">IntelliSense при отключенном параметре Option Infer</span><span class="sxs-lookup"><span data-stu-id="7ab93-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ab93-126">Если переменная объявлена как `Object`, тип времени выполнения может измениться в ходе работы программы.</span><span class="sxs-lookup"><span data-stu-id="7ab93-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> <span data-ttu-id="7ab93-127">Visual Basic выполняет операции *упаковки-преобразования* и *распаковки* для преобразования между `Object` и типом значения, что замедляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="7ab93-127">Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="7ab93-128">Сведения об упаковке и распаковке см. в разделе [спецификация языка Visual Basic](~/_vblang/spec/conversions.md#value-type-conversions).</span><span class="sxs-lookup"><span data-stu-id="7ab93-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).</span></span>
  
 <span data-ttu-id="7ab93-129">Определение типов применяется на уровне процедур и не применяется вне процедур в классах, структурах, модулях и интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="7ab93-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="7ab93-130">Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="7ab93-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="7ab93-131">Если оператор Option Infer отсутствует</span><span class="sxs-lookup"><span data-stu-id="7ab93-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="7ab93-132">Если исходный код не содержит `Option Infer` инструкции **Option Infer** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="7ab93-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="7ab93-133">Если используется компилятор командной строки, [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="7ab93-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="7ab93-134">Чтобы включить Option Infer в среде разработки</span><span class="sxs-lookup"><span data-stu-id="7ab93-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="7ab93-135">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7ab93-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="7ab93-136">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7ab93-136">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7ab93-137">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="7ab93-137">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="7ab93-138">Задайте значение в **Option infer** поле.</span><span class="sxs-lookup"><span data-stu-id="7ab93-138">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="7ab93-139">При создании нового проекта, **Option Infer** на **компиляции** набор вкладок **Option Infer** в **Visual Basic по умолчанию** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="7ab93-139">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="7ab93-140">Чтобы получить доступ к **Visual Basic по умолчанию** диалоговом окне **средства** меню, щелкните **параметры**.</span><span class="sxs-lookup"><span data-stu-id="7ab93-140">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="7ab93-141">В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="7ab93-141">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="7ab93-142">Начальная настройка по умолчанию в **параметры Visualbasic по умолчанию** является `On`.</span><span class="sxs-lookup"><span data-stu-id="7ab93-142">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="7ab93-143">Чтобы включить Option Infer в командной строке</span><span class="sxs-lookup"><span data-stu-id="7ab93-143">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="7ab93-144">Включить [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) параметр компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="7ab93-144">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="7ab93-145">Типы данных и значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7ab93-145">Default Data Types and Values</span></span>  
 <span data-ttu-id="7ab93-146">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="7ab93-146">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="7ab93-147">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="7ab93-147">Data type specified?</span></span>|<span data-ttu-id="7ab93-148">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="7ab93-148">Initializer specified?</span></span>|<span data-ttu-id="7ab93-149">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab93-149">Example</span></span>|<span data-ttu-id="7ab93-150">Результат</span><span class="sxs-lookup"><span data-stu-id="7ab93-150">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="7ab93-151">Нет</span><span class="sxs-lookup"><span data-stu-id="7ab93-151">No</span></span>|<span data-ttu-id="7ab93-152">Нет</span><span class="sxs-lookup"><span data-stu-id="7ab93-152">No</span></span>|`Dim qty`|<span data-ttu-id="7ab93-153">Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7ab93-153">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="7ab93-154">Если параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="7ab93-154">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="7ab93-155">Нет</span><span class="sxs-lookup"><span data-stu-id="7ab93-155">No</span></span>|<span data-ttu-id="7ab93-156">Да</span><span class="sxs-lookup"><span data-stu-id="7ab93-156">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="7ab93-157">Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора.</span><span class="sxs-lookup"><span data-stu-id="7ab93-157">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="7ab93-158">См. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="7ab93-158">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="7ab93-159">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="7ab93-159">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="7ab93-160">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="7ab93-160">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="7ab93-161">Да</span><span class="sxs-lookup"><span data-stu-id="7ab93-161">Yes</span></span>|<span data-ttu-id="7ab93-162">Нет</span><span class="sxs-lookup"><span data-stu-id="7ab93-162">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="7ab93-163">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="7ab93-163">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="7ab93-164">Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7ab93-164">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="7ab93-165">Да</span><span class="sxs-lookup"><span data-stu-id="7ab93-165">Yes</span></span>|<span data-ttu-id="7ab93-166">Да</span><span class="sxs-lookup"><span data-stu-id="7ab93-166">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="7ab93-167">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="7ab93-167">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7ab93-168">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab93-168">Example</span></span>  
 <span data-ttu-id="7ab93-169">В следующих примерах показано, как оператор `Option Infer` включает локальное определение типов.</span><span class="sxs-lookup"><span data-stu-id="7ab93-169">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="7ab93-170">Пример</span><span class="sxs-lookup"><span data-stu-id="7ab93-170">Example</span></span>  
 <span data-ttu-id="7ab93-171">В следующем примере показано, что тип времени выполнения может различаться, когда переменная указана как `Object`.</span><span class="sxs-lookup"><span data-stu-id="7ab93-171">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="7ab93-172">См. также</span><span class="sxs-lookup"><span data-stu-id="7ab93-172">See also</span></span>
- [<span data-ttu-id="7ab93-173">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="7ab93-173">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="7ab93-174">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="7ab93-174">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="7ab93-175">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="7ab93-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="7ab93-176">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="7ab93-176">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="7ab93-177">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="7ab93-177">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="7ab93-178">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="7ab93-178">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="7ab93-179">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="7ab93-179">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="7ab93-180">Упаковка-преобразование и распаковка-преобразование</span><span class="sxs-lookup"><span data-stu-id="7ab93-180">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
