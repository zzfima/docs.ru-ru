---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 1de1b3a816739fc5f8ba1d1251b673c0b708d106
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969496"
---
# <a name="-optionexplicit"></a><span data-ttu-id="f9c51-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="f9c51-102">-optionexplicit</span></span>
<span data-ttu-id="f9c51-103">Указывает компилятору для сообщения об ошибках, если переменные не объявлены, прежде чем они используются.</span><span class="sxs-lookup"><span data-stu-id="f9c51-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9c51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9c51-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9c51-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f9c51-105">Arguments</span></span>  
 <span data-ttu-id="f9c51-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f9c51-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="f9c51-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f9c51-107">Optional.</span></span> <span data-ttu-id="f9c51-108">Укажите `-optionexplicit+` требуется явное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="f9c51-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="f9c51-109">`-optionexplicit+` — Это значение по умолчанию, так же, как `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="f9c51-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="f9c51-110">`-optionexplicit-` Позволяет неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="f9c51-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9c51-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9c51-111">Remarks</span></span>  
 <span data-ttu-id="f9c51-112">Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), то оператор переопределяет `-optionexplicit` параметр компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="f9c51-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="f9c51-113">Чтобы задать - optionexplicit в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9c51-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="f9c51-114">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="f9c51-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f9c51-115">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f9c51-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="f9c51-116">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="f9c51-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="f9c51-117">Измените значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="f9c51-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9c51-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f9c51-118">Example</span></span>  
 <span data-ttu-id="f9c51-119">Следующий код компилируется при `-optionexplicit-` используется.</span><span class="sxs-lookup"><span data-stu-id="f9c51-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="f9c51-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f9c51-120">See also</span></span>
- [<span data-ttu-id="f9c51-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="f9c51-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f9c51-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="f9c51-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="f9c51-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="f9c51-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="f9c51-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="f9c51-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="f9c51-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="f9c51-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="f9c51-126">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="f9c51-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="f9c51-127">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="f9c51-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
