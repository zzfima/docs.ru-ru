---
title: "/ optionexplicit | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
dev_langs:
- VB
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
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
ms.openlocfilehash: 3d2622c08b863233c8e1088bad252b37b3b38b04
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="optionexplicit"></a><span data-ttu-id="c9333-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="c9333-102">/optionexplicit</span></span>
<span data-ttu-id="c9333-103">Указывает компилятору сообщать об ошибках, если переменная не объявлена, прежде чем их использовать.</span><span class="sxs-lookup"><span data-stu-id="c9333-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9333-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9333-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9333-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c9333-105">Arguments</span></span>  
 <span data-ttu-id="c9333-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c9333-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c9333-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c9333-107">Optional.</span></span> <span data-ttu-id="c9333-108">Укажите `/optionexplicit+` явного объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="c9333-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="c9333-109">`/optionexplicit+` Параметр по умолчанию и является таким же, как `/optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="c9333-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="c9333-110">`/optionexplicit-` Параметр позволяет выполнять неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="c9333-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9333-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9333-111">Remarks</span></span>  
 <span data-ttu-id="c9333-112">Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), то оператор переопределяет `/optionexplicit` параметр компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="c9333-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="c9333-113">Чтобы задать дополнительные в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c9333-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="c9333-114">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c9333-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c9333-115">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="c9333-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="c9333-116">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="c9333-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="c9333-117">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c9333-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="c9333-118">Измените значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="c9333-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9333-119">Пример</span><span class="sxs-lookup"><span data-stu-id="c9333-119">Example</span></span>  
 <span data-ttu-id="c9333-120">Следующий код компилируется при `/optionexplicit-` используется.</span><span class="sxs-lookup"><span data-stu-id="c9333-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 <span data-ttu-id="c9333-121">[!code-vb[VbVbalrCompiler&#5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c9333-121">[!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9333-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c9333-122">See Also</span></span>  
 <span data-ttu-id="c9333-123">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c9333-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c9333-124"> [Дополнительные](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="c9333-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="c9333-125"> [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="c9333-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="c9333-126"> [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="c9333-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="c9333-127"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="c9333-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="c9333-128"> [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c9333-128"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="c9333-129"> [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="c9333-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
