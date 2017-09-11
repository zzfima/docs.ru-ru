---
title: "/ optioninfer | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
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
ms.openlocfilehash: 4bcc35da2a255ca75805c8a918027d2ccb61b154
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="optioninfer"></a><span data-ttu-id="5e949-102">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="5e949-102">/optioninfer</span></span>
<span data-ttu-id="5e949-103">Включает использование локального определения типов в различных объявлениях.</span><span class="sxs-lookup"><span data-stu-id="5e949-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e949-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e949-104">Syntax</span></span>  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5e949-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5e949-105">Arguments</span></span>  
  
|<span data-ttu-id="5e949-106">Термин</span><span class="sxs-lookup"><span data-stu-id="5e949-106">Term</span></span>|<span data-ttu-id="5e949-107">Определение</span><span class="sxs-lookup"><span data-stu-id="5e949-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="5e949-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5e949-108">`+` &#124; `-`</span></span>|<span data-ttu-id="5e949-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5e949-109">Optional.</span></span> <span data-ttu-id="5e949-110">Укажите `/optioninfer+`, чтобы включить локальное определение типов, или `/optioninfer-`, чтобы заблокировать его.</span><span class="sxs-lookup"><span data-stu-id="5e949-110">Specify `/optioninfer+` to enable local type inference, or `/optioninfer-` to block it.</span></span> <span data-ttu-id="5e949-111">Параметр `/optioninfer`, для которого не указано значение, действует так же, как `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="5e949-111">The `/optioninfer` option, with no value specified, is the same as `/optioninfer+`.</span></span> <span data-ttu-id="5e949-112">Значение по умолчанию при отсутствии параметра `/optioninfer` также равно `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="5e949-112">The default value when the `/optioninfer` switch is not present is also `/optioninfer+`.</span></span> <span data-ttu-id="5e949-113">Значение по умолчанию задается в файле ответов Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="5e949-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5e949-114">Можно использовать параметр `/noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="5e949-114">You can use the `/noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="5e949-115">Значение компилятора по умолчанию для этого параметра — `/optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="5e949-115">The compiler default for this option is `/optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e949-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e949-116">Remarks</span></span>  
 <span data-ttu-id="5e949-117">Если файл исходного кода содержит [Option Infer оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md), то оператор переопределяет `/optioninfer` параметр компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="5e949-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `/optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="5e949-118">Чтобы задать параметр /optioninfer в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5e949-118">To set /optioninfer in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="5e949-119">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="5e949-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="5e949-120">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="5e949-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="5e949-121">Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="5e949-121">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="5e949-122">На **компиляции** измените значение в **Option infer** поле.</span><span class="sxs-lookup"><span data-stu-id="5e949-122">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e949-123">Пример</span><span class="sxs-lookup"><span data-stu-id="5e949-123">Example</span></span>  
 <span data-ttu-id="5e949-124">Следующий код компилирует `test.vb` с включенным локальным определением типов.</span><span class="sxs-lookup"><span data-stu-id="5e949-124">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e949-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5e949-125">See Also</span></span>  
 <span data-ttu-id="5e949-126">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="5e949-127"> [Дополнительные](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-127"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="5e949-128"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-128"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="5e949-129"> [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-129"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="5e949-130"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="5e949-131"> [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-131"> [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="5e949-132"> [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="5e949-133"> [Диалоговое окно параметров значения по умолчанию, проекты, Visual Basic](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span><span class="sxs-lookup"><span data-stu-id="5e949-133"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span></span>  
<span data-ttu-id="5e949-134"> [Страница "Компиляция" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="5e949-134"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="5e949-135"> [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="5e949-135"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="5e949-136"> [Построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span><span class="sxs-lookup"><span data-stu-id="5e949-136"> [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span></span>
