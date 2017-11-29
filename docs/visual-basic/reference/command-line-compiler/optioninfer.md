---
title: /optioninfer
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4400ee58214c8f9990d4b123e17ef0f6553a5a69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optioninfer"></a><span data-ttu-id="b49d1-102">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="b49d1-102">/optioninfer</span></span>
<span data-ttu-id="b49d1-103">Включает использование локального определения типов в различных объявлениях.</span><span class="sxs-lookup"><span data-stu-id="b49d1-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b49d1-104">Syntax</span></span>  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b49d1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b49d1-105">Arguments</span></span>  
  
|<span data-ttu-id="b49d1-106">Термин</span><span class="sxs-lookup"><span data-stu-id="b49d1-106">Term</span></span>|<span data-ttu-id="b49d1-107">Определение</span><span class="sxs-lookup"><span data-stu-id="b49d1-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="b49d1-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b49d1-108">`+` &#124; `-`</span></span>|<span data-ttu-id="b49d1-109">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b49d1-109">Optional.</span></span> <span data-ttu-id="b49d1-110">Укажите `/optioninfer+`, чтобы включить локальное определение типов, или `/optioninfer-`, чтобы заблокировать его.</span><span class="sxs-lookup"><span data-stu-id="b49d1-110">Specify `/optioninfer+` to enable local type inference, or `/optioninfer-` to block it.</span></span> <span data-ttu-id="b49d1-111">Параметр `/optioninfer`, для которого не указано значение, действует так же, как `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="b49d1-111">The `/optioninfer` option, with no value specified, is the same as `/optioninfer+`.</span></span> <span data-ttu-id="b49d1-112">Значение по умолчанию при отсутствии параметра `/optioninfer` также равно `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="b49d1-112">The default value when the `/optioninfer` switch is not present is also `/optioninfer+`.</span></span> <span data-ttu-id="b49d1-113">Значение по умолчанию задается в файле ответов Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="b49d1-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b49d1-114">Можно использовать параметр `/noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="b49d1-114">You can use the `/noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="b49d1-115">Значение компилятора по умолчанию для этого параметра — `/optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="b49d1-115">The compiler default for this option is `/optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b49d1-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="b49d1-116">Remarks</span></span>  
 <span data-ttu-id="b49d1-117">Если файл исходного кода содержит [Option Infer-оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md), переопределяет инструкцию `/optioninfer` параметр компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="b49d1-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `/optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="b49d1-118">Чтобы задать параметр /optioninfer в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b49d1-118">To set /optioninfer in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="b49d1-119">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="b49d1-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="b49d1-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b49d1-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="b49d1-121">Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="b49d1-121">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="b49d1-122">На **компиляции** измените значение в **Option infer** поле.</span><span class="sxs-lookup"><span data-stu-id="b49d1-122">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b49d1-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b49d1-123">Example</span></span>  
 <span data-ttu-id="b49d1-124">Следующий код компилирует `test.vb` с включенным локальным определением типов.</span><span class="sxs-lookup"><span data-stu-id="b49d1-124">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b49d1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b49d1-125">See Also</span></span>  
 [<span data-ttu-id="b49d1-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b49d1-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b49d1-127">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="b49d1-127">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="b49d1-128">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="b49d1-128">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="b49d1-129">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="b49d1-129">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="b49d1-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="b49d1-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b49d1-131">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="b49d1-131">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="b49d1-132">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="b49d1-132">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="b49d1-133">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="b49d1-133">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="b49d1-134">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49d1-134">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="b49d1-135">/noconfig</span><span class="sxs-lookup"><span data-stu-id="b49d1-135">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="b49d1-136">Построение из командной строки</span><span class="sxs-lookup"><span data-stu-id="b49d1-136">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
