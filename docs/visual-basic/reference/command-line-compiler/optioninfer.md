---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: c6fc7e9dcfbce938ad75b0f357c2bfa9cd10703a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005322"
---
# <a name="-optioninfer"></a><span data-ttu-id="2aeab-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="2aeab-102">-optioninfer</span></span>
<span data-ttu-id="2aeab-103">Включает использование локального определения типов в различных объявлениях.</span><span class="sxs-lookup"><span data-stu-id="2aeab-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aeab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2aeab-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2aeab-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2aeab-105">Arguments</span></span>  
  
|<span data-ttu-id="2aeab-106">Термин</span><span class="sxs-lookup"><span data-stu-id="2aeab-106">Term</span></span>|<span data-ttu-id="2aeab-107">Определение</span><span class="sxs-lookup"><span data-stu-id="2aeab-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2aeab-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2aeab-108">`+` &#124; `-`</span></span>|<span data-ttu-id="2aeab-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2aeab-109">Optional.</span></span> <span data-ttu-id="2aeab-110">Укажите `-optioninfer+`, чтобы включить локальное определение типов, или `-optioninfer-`, чтобы заблокировать его.</span><span class="sxs-lookup"><span data-stu-id="2aeab-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="2aeab-111">Параметр `-optioninfer`, для которого не указано значение, действует так же, как `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="2aeab-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="2aeab-112">Значение по умолчанию при отсутствии параметра `-optioninfer` также равно `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="2aeab-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="2aeab-113">Значение по умолчанию задается в файле ответов Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="2aeab-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="2aeab-114">Можно использовать параметр `-noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="2aeab-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="2aeab-115">Значение компилятора по умолчанию для этого параметра — `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="2aeab-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2aeab-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2aeab-116">Remarks</span></span>  
 <span data-ttu-id="2aeab-117">Если файл исходного кода содержит [инструкцию Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md), инструкция переопределяет параметр компилятора командной строки `-optioninfer`.</span><span class="sxs-lookup"><span data-stu-id="2aeab-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="2aeab-118">Установка параметра-оптионинфер в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2aeab-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="2aeab-119">Выберите проект в **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="2aeab-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="2aeab-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2aeab-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="2aeab-121">На вкладке **Компиляция** измените значение в поле **параметр Infer** .</span><span class="sxs-lookup"><span data-stu-id="2aeab-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aeab-122">Пример</span><span class="sxs-lookup"><span data-stu-id="2aeab-122">Example</span></span>  
 <span data-ttu-id="2aeab-123">Следующий код компилирует `test.vb` с включенным локальным определением типов.</span><span class="sxs-lookup"><span data-stu-id="2aeab-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2aeab-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2aeab-124">See also</span></span>

- [<span data-ttu-id="2aeab-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2aeab-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2aeab-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="2aeab-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="2aeab-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="2aeab-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="2aeab-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="2aeab-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="2aeab-129">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2aeab-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2aeab-130">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="2aeab-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="2aeab-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="2aeab-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="2aeab-132">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="2aeab-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="2aeab-133">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aeab-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="2aeab-134">/noconfig</span><span class="sxs-lookup"><span data-stu-id="2aeab-134">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="2aeab-135">Построение из командной строки</span><span class="sxs-lookup"><span data-stu-id="2aeab-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
