---
title: "Option Explicit-оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
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
ms.openlocfilehash: 4283599d9ed2ad9075ab0b2f404f1a12a31437ec
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="80b3a-102">Оператор Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80b3a-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="80b3a-103">Вызывает принудительное явное объявление всех переменных в файле или допускает неявного объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="80b3a-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80b3a-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="80b3a-105">Части</span><span class="sxs-lookup"><span data-stu-id="80b3a-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="80b3a-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="80b3a-106">Optional.</span></span> <span data-ttu-id="80b3a-107">Позволяет `Option Explicit` проверки.</span><span class="sxs-lookup"><span data-stu-id="80b3a-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="80b3a-108">Если `On` или `Off` не указан, значение по умолчанию — `On`.</span><span class="sxs-lookup"><span data-stu-id="80b3a-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="80b3a-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="80b3a-109">Optional.</span></span> <span data-ttu-id="80b3a-110">Отключает `Option Explicit` проверки.</span><span class="sxs-lookup"><span data-stu-id="80b3a-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80b3a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="80b3a-111">Remarks</span></span>  
 <span data-ttu-id="80b3a-112">Когда `Option Explicit On` или `Option Explicit` появится в файле, необходимо явно объявить все переменные с помощью `Dim` или `ReDim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="80b3a-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="80b3a-113">При попытке использовать необъявленное имя переменной, происходит ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="80b3a-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="80b3a-114">`Option Explicit Off` Оператор разрешает неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="80b3a-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="80b3a-115">Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.</span><span class="sxs-lookup"><span data-stu-id="80b3a-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80b3a-116">Установка `Option Explicit` для `Off` обычно не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="80b3a-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="80b3a-117">Имя переменной в одно или несколько расположений, что может привести к непредвиденным результатам при выполнении программы может опечатка.</span><span class="sxs-lookup"><span data-stu-id="80b3a-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="80b3a-118">Если оператор Option Explicit не присутствует</span><span class="sxs-lookup"><span data-stu-id="80b3a-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="80b3a-119">Если исходный код не содержит `Option Explicit` инструкции, **Option Explicit** на [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="80b3a-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="80b3a-120">Если используется компилятор командной строки, [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="80b3a-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="80b3a-121">Чтобы задать режим Explicit в Интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="80b3a-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="80b3a-122">В **обозревателе**, выберите проект.</span><span class="sxs-lookup"><span data-stu-id="80b3a-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="80b3a-123">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="80b3a-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="80b3a-124">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="80b3a-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="80b3a-125">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="80b3a-125">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="80b3a-126">Задайте значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="80b3a-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="80b3a-127">При создании нового проекта, **Option Explicit** на **компиляции** задано значение **Option Explicit** в **VB по умолчанию** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="80b3a-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="80b3a-128">Для доступа к **VB по умолчанию** в диалоговом **средства** меню, щелкните **параметры**.</span><span class="sxs-lookup"><span data-stu-id="80b3a-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="80b3a-129">В **параметры** диалогового окна разверните **проекты и решения**и нажмите кнопку **VB по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="80b3a-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="80b3a-130">Начальный параметр по умолчанию в **VB значения по умолчанию** — `On`.</span><span class="sxs-lookup"><span data-stu-id="80b3a-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="80b3a-131">Чтобы задать режим Explicit в командной строке</span><span class="sxs-lookup"><span data-stu-id="80b3a-131">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="80b3a-132">Включить [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) параметра компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="80b3a-132">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80b3a-133">Пример</span><span class="sxs-lookup"><span data-stu-id="80b3a-133">Example</span></span>  
 <span data-ttu-id="80b3a-134">В следующем примере используется `Option Explicit` инструкции, чтобы обеспечить явное объявление всех переменных.</span><span class="sxs-lookup"><span data-stu-id="80b3a-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="80b3a-135">Попытка использования необъявленных переменных приводит к ошибке во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="80b3a-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 <span data-ttu-id="80b3a-136">[!code-vb[VbVbalrStatements&#47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="80b3a-136">[!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="80b3a-137">[!code-vb[VbVbalrStatements&#48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="80b3a-137">[!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b3a-138">См. также</span><span class="sxs-lookup"><span data-stu-id="80b3a-138">See Also</span></span>  
 <span data-ttu-id="80b3a-139">[Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-139">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="80b3a-140"> [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-140"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="80b3a-141"> [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-141"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="80b3a-142"> [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-142"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="80b3a-143"> [Дополнительные](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-143"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="80b3a-144"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-144"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="80b3a-145"> [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="80b3a-145"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="80b3a-146"> [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="80b3a-146"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
