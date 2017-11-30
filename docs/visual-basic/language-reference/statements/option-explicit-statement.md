---
title: "Оператор Option Explicit (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d39b3d7cf5096e3b263938d32e017eae5708e042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="7a008-102">Оператор Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a008-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="7a008-103">Принудительное явное объявление всех переменных в файле, либо разрешает неявные объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="7a008-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a008-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a008-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="7a008-105">Части</span><span class="sxs-lookup"><span data-stu-id="7a008-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="7a008-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7a008-106">Optional.</span></span> <span data-ttu-id="7a008-107">Позволяет `Option Explicit` проверки.</span><span class="sxs-lookup"><span data-stu-id="7a008-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="7a008-108">Если `On` или `Off` не указан, значение по умолчанию — `On`.</span><span class="sxs-lookup"><span data-stu-id="7a008-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="7a008-109">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7a008-109">Optional.</span></span> <span data-ttu-id="7a008-110">Отключает `Option Explicit` проверки.</span><span class="sxs-lookup"><span data-stu-id="7a008-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a008-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a008-111">Remarks</span></span>  
 <span data-ttu-id="7a008-112">Когда `Option Explicit On` или `Option Explicit` появится в файле, все переменные должны быть объявлены явно с помощью `Dim` или `ReDim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7a008-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="7a008-113">При попытке использовать необъявленное имя переменной, произошла ошибка во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7a008-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="7a008-114">`Option Explicit Off` Оператор разрешает неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="7a008-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="7a008-115">Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.</span><span class="sxs-lookup"><span data-stu-id="7a008-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a008-116">Установка `Option Explicit` для `Off` обычно это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="7a008-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="7a008-117">Удалось написания имени переменной в одно или несколько расположений, которые бы привести к непредвиденным результатам при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="7a008-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="7a008-118">Если оператор Option Explicit отсутствует</span><span class="sxs-lookup"><span data-stu-id="7a008-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="7a008-119">Если исходный код не содержит `Option Explicit` инструкции **Option Explicit** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="7a008-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="7a008-120">При использовании компилятора командной строки [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="7a008-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="7a008-121">Чтобы задать Option Explicit в Интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="7a008-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="7a008-122">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7a008-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="7a008-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7a008-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="7a008-124">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="7a008-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="7a008-125">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="7a008-125">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="7a008-126">Задайте значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="7a008-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="7a008-127">При создании нового проекта **Option Explicit** на **компиляции** набор вкладок **Option Explicit** в **VB по умолчанию**диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="7a008-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="7a008-128">Чтобы получить доступ к **VB по умолчанию** в диалоговом **средства** меню, нажмите кнопку **параметры**.</span><span class="sxs-lookup"><span data-stu-id="7a008-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="7a008-129">В **параметры** диалогового окна разверните **проекты и решения**, а затем нажмите кнопку **VB по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="7a008-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="7a008-130">Начальный параметр по умолчанию в **VB значения по умолчанию** — `On`.</span><span class="sxs-lookup"><span data-stu-id="7a008-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="7a008-131">Чтобы задать Option Explicit в командной строке</span><span class="sxs-lookup"><span data-stu-id="7a008-131">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="7a008-132">Включить [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) параметра компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="7a008-132">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a008-133">Пример</span><span class="sxs-lookup"><span data-stu-id="7a008-133">Example</span></span>  
 <span data-ttu-id="7a008-134">В следующем примере используется `Option Explicit` инструкцию, чтобы обеспечить явное объявление всех переменных.</span><span class="sxs-lookup"><span data-stu-id="7a008-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="7a008-135">Попытка использования необъявленных переменных приводит к ошибке во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7a008-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7a008-136">См. также</span><span class="sxs-lookup"><span data-stu-id="7a008-136">See Also</span></span>  
 [<span data-ttu-id="7a008-137">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="7a008-137">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="7a008-138">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="7a008-138">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="7a008-139">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="7a008-139">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="7a008-140">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="7a008-140">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="7a008-141">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="7a008-141">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="7a008-142">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="7a008-142">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="7a008-143">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="7a008-143">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="7a008-144">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="7a008-144">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
