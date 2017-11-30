---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1cfdb94ebafa7d6a14253aeb59ab98b3a953fe4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optionexplicit"></a><span data-ttu-id="16326-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="16326-102">/optionexplicit</span></span>
<span data-ttu-id="16326-103">Указывает компилятору на отправку отчетов об ошибках, если переменная не объявлена до их использования.</span><span class="sxs-lookup"><span data-stu-id="16326-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16326-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16326-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="16326-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="16326-105">Arguments</span></span>  
 <span data-ttu-id="16326-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="16326-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="16326-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="16326-107">Optional.</span></span> <span data-ttu-id="16326-108">Укажите `/optionexplicit+` явного объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="16326-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="16326-109">`/optionexplicit+` Параметр используется по умолчанию и совпадает со значением `/optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="16326-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="16326-110">`/optionexplicit-` Режим обеспечивает неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="16326-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16326-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="16326-111">Remarks</span></span>  
 <span data-ttu-id="16326-112">Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), переопределяет инструкцию `/optionexplicit` параметр компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="16326-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="16326-113">Задание/optionexplicit в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="16326-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="16326-114">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="16326-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="16326-115">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="16326-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="16326-116">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="16326-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="16326-117">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="16326-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="16326-118">Измените значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="16326-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16326-119">Пример</span><span class="sxs-lookup"><span data-stu-id="16326-119">Example</span></span>  
 <span data-ttu-id="16326-120">Следующий код компилируется при `/optionexplicit-` используется.</span><span class="sxs-lookup"><span data-stu-id="16326-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="16326-121">См. также</span><span class="sxs-lookup"><span data-stu-id="16326-121">See Also</span></span>  
 [<span data-ttu-id="16326-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="16326-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="16326-123">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="16326-123">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="16326-124">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="16326-124">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="16326-125">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="16326-125">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="16326-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="16326-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="16326-127">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="16326-127">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="16326-128">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="16326-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
