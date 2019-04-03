---
title: Оператор Option Explicit (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c42dd74ea0dc01b8ae7ffb7eb04737a9784625a9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841463"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="becc3-102">Оператор Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="becc3-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="becc3-103">Принудительное явное объявление всех переменных в файле или неявного объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="becc3-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="becc3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="becc3-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="becc3-105">Части</span><span class="sxs-lookup"><span data-stu-id="becc3-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="becc3-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="becc3-106">Optional.</span></span> <span data-ttu-id="becc3-107">Позволяет `Option Explicit` проверки.</span><span class="sxs-lookup"><span data-stu-id="becc3-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="becc3-108">Если `On` или `Off` не указан, по умолчанию используется `On`.</span><span class="sxs-lookup"><span data-stu-id="becc3-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="becc3-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="becc3-109">Optional.</span></span> <span data-ttu-id="becc3-110">Отключает `Option Explicit` проверки.</span><span class="sxs-lookup"><span data-stu-id="becc3-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="becc3-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="becc3-111">Remarks</span></span>  
 <span data-ttu-id="becc3-112">Когда `Option Explicit On` или `Option Explicit` появится в файле, необходимо явно объявить все переменные с помощью `Dim` или `ReDim` инструкций.</span><span class="sxs-lookup"><span data-stu-id="becc3-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="becc3-113">Если вы попытаетесь использовать необъявленных переменных, возникает ошибка во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="becc3-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="becc3-114">`Option Explicit Off` Оператор обеспечивает неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="becc3-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="becc3-115">Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.</span><span class="sxs-lookup"><span data-stu-id="becc3-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="becc3-116">Установка `Option Explicit` для `Off` обычно не является хорошей практикой.</span><span class="sxs-lookup"><span data-stu-id="becc3-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="becc3-117">Вы можете допустить ошибку при вводе имени переменной в одном или нескольких местах, что приведет к непредвиденным результатам при выполнении программы.</span><span class="sxs-lookup"><span data-stu-id="becc3-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="becc3-118">Если оператор Option Explicit отсутствует</span><span class="sxs-lookup"><span data-stu-id="becc3-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="becc3-119">Если исходный код не содержит `Option Explicit` инструкции **Option Explicit** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="becc3-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="becc3-120">Если используется компилятор командной строки, [дополнительные](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="becc3-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="becc3-121">Чтобы задать Option Explicit в интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="becc3-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="becc3-122">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="becc3-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="becc3-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="becc3-123">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="becc3-124">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="becc3-124">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="becc3-125">Задайте значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="becc3-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="becc3-126">При создании нового проекта, **Option Explicit** на **компиляции** набор вкладок **Option Explicit** в **Visual Basic по умолчанию**диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="becc3-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="becc3-127">Чтобы получить доступ к **Visual Basic по умолчанию** диалоговом окне **средства** меню, щелкните **параметры**.</span><span class="sxs-lookup"><span data-stu-id="becc3-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="becc3-128">В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="becc3-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="becc3-129">Начальная настройка по умолчанию в **параметры Visualbasic по умолчанию** является `On`.</span><span class="sxs-lookup"><span data-stu-id="becc3-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="becc3-130">Чтобы задать Option Explicit в командной строке</span><span class="sxs-lookup"><span data-stu-id="becc3-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="becc3-131">Включить [дополнительные](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) параметр компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="becc3-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="becc3-132">Пример</span><span class="sxs-lookup"><span data-stu-id="becc3-132">Example</span></span>  
 <span data-ttu-id="becc3-133">В следующем примере используется `Option Explicit` инструкцию, чтобы обеспечить явное объявление всех переменных.</span><span class="sxs-lookup"><span data-stu-id="becc3-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="becc3-134">Попытка использования необъявленных переменных приводит к ошибке во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="becc3-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="becc3-135">См. также</span><span class="sxs-lookup"><span data-stu-id="becc3-135">See also</span></span>

- [<span data-ttu-id="becc3-136">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="becc3-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="becc3-137">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="becc3-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="becc3-138">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="becc3-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="becc3-139">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="becc3-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="becc3-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="becc3-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="becc3-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="becc3-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="becc3-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="becc3-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="becc3-143">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="becc3-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
