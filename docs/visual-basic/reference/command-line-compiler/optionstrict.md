---
title: /optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 692681b21c243432ec8e7160bcc1eaa4e718d64d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="optionstrict"></a><span data-ttu-id="2561e-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="2561e-102">/optionstrict</span></span>
<span data-ttu-id="2561e-103">Требовать строгой семантики для ограничения неявного преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="2561e-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2561e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2561e-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2561e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2561e-105">Arguments</span></span>  
 <span data-ttu-id="2561e-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2561e-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2561e-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="2561e-107">Optional.</span></span> <span data-ttu-id="2561e-108">`/optionstrict+` Ограничивает неявное преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="2561e-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="2561e-109">Значение по умолчанию для этого параметра — `/optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="2561e-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="2561e-110">`/optionstrict+` Параметр совпадает со значением `/optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="2561e-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="2561e-111">Можно использовать как для разрешающей семантики.</span><span class="sxs-lookup"><span data-stu-id="2561e-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="2561e-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="2561e-112">Required.</span></span> <span data-ttu-id="2561e-113">Предупреждать, когда не накладывается ограничение на строгую семантику языка.</span><span class="sxs-lookup"><span data-stu-id="2561e-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2561e-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="2561e-114">Remarks</span></span>  
 <span data-ttu-id="2561e-115">Когда `/optionstrict+` действует, неявно могут выполняться только расширяющие преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="2561e-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="2561e-116">Неявные преобразования типов, например для присвоения `Decimal` типом объекта в объект типа integer, помечаются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="2561e-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="2561e-117">Для создания предупреждения для неявных сужающих преобразований типа, используйте `/optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="2561e-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="2561e-118">Используйте `/nowarn:numberlist` игнорировать определенных предупреждений и `/warnaserror:numberlist` обрабатывать конкретного предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="2561e-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="2561e-119">Чтобы задать дополнительные сведения в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2561e-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="2561e-120">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="2561e-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2561e-121">На **проекта** меню, нажмите кнопку **свойства.**</span><span class="sxs-lookup"><span data-stu-id="2561e-121">On the **Project** menu, click **Properties.**</span></span>   
  
2.  <span data-ttu-id="2561e-122">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="2561e-122">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="2561e-123">Измените значение в **Option Strict** поле.</span><span class="sxs-lookup"><span data-stu-id="2561e-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="2561e-124">Чтобы установить/optionstrict программными средствами</span><span class="sxs-lookup"><span data-stu-id="2561e-124">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="2561e-125">В разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2561e-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2561e-126">Пример</span><span class="sxs-lookup"><span data-stu-id="2561e-126">Example</span></span>  
 <span data-ttu-id="2561e-127">Следующий код компилирует `Test.vb` с помощью строгой семантики.</span><span class="sxs-lookup"><span data-stu-id="2561e-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2561e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2561e-128">See Also</span></span>  
 [<span data-ttu-id="2561e-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2561e-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2561e-130">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="2561e-130">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="2561e-131">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="2561e-131">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="2561e-132">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="2561e-132">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="2561e-133">/nowarn</span><span class="sxs-lookup"><span data-stu-id="2561e-133">/nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [<span data-ttu-id="2561e-134">/ warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2561e-134">/warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [<span data-ttu-id="2561e-135">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2561e-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="2561e-136">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="2561e-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="2561e-137">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="2561e-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
