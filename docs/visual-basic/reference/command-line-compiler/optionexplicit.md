---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e701addb31b361e55f2761f441c23deaef7c10d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="optionexplicit"></a><span data-ttu-id="7e3bc-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="7e3bc-102">/optionexplicit</span></span>
<span data-ttu-id="7e3bc-103">Указывает компилятору на отправку отчетов об ошибках, если переменная не объявлена до их использования.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e3bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e3bc-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e3bc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7e3bc-105">Arguments</span></span>  
 <span data-ttu-id="7e3bc-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7e3bc-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="7e3bc-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-107">Optional.</span></span> <span data-ttu-id="7e3bc-108">Укажите `/optionexplicit+` явного объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="7e3bc-109">`/optionexplicit+` Параметр используется по умолчанию и совпадает со значением `/optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="7e3bc-110">`/optionexplicit-` Режим обеспечивает неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e3bc-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e3bc-111">Remarks</span></span>  
 <span data-ttu-id="7e3bc-112">Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), переопределяет инструкцию `/optionexplicit` параметр компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="7e3bc-113">Задание/optionexplicit в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7e3bc-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="7e3bc-114">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7e3bc-115">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="7e3bc-116">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="7e3bc-117">Измените значение в **Option Explicit** поле.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e3bc-118">Пример</span><span class="sxs-lookup"><span data-stu-id="7e3bc-118">Example</span></span>  
 <span data-ttu-id="7e3bc-119">Следующий код компилируется при `/optionexplicit-` используется.</span><span class="sxs-lookup"><span data-stu-id="7e3bc-119">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7e3bc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7e3bc-120">See Also</span></span>  
 [<span data-ttu-id="7e3bc-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7e3bc-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="7e3bc-122">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="7e3bc-122">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="7e3bc-123">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="7e3bc-123">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="7e3bc-124">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="7e3bc-124">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="7e3bc-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7e3bc-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="7e3bc-126">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="7e3bc-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="7e3bc-127">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="7e3bc-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
