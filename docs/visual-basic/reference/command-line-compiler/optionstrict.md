---
title: /optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f783cc5b20c4fe6d7812a05a66cbc4cdfc0b9395
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optionstrict"></a><span data-ttu-id="2de1b-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="2de1b-102">/optionstrict</span></span>
<span data-ttu-id="2de1b-103">Требовать строгой семантики для ограничения неявного преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="2de1b-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2de1b-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2de1b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2de1b-105">Arguments</span></span>  
 <span data-ttu-id="2de1b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2de1b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2de1b-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="2de1b-107">Optional.</span></span> <span data-ttu-id="2de1b-108">`/optionstrict+` Ограничивает неявное преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="2de1b-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="2de1b-109">Значение по умолчанию для этого параметра — `/optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="2de1b-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="2de1b-110">`/optionstrict+` Параметр совпадает со значением `/optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="2de1b-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="2de1b-111">Можно использовать как для разрешающей семантики.</span><span class="sxs-lookup"><span data-stu-id="2de1b-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="2de1b-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2de1b-112">Required.</span></span> <span data-ttu-id="2de1b-113">Предупреждать, когда не накладывается ограничение на строгую семантику языка.</span><span class="sxs-lookup"><span data-stu-id="2de1b-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2de1b-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="2de1b-114">Remarks</span></span>  
 <span data-ttu-id="2de1b-115">Когда `/optionstrict+` действует, неявно могут выполняться только расширяющие преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="2de1b-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="2de1b-116">Неявные преобразования типов, например для присвоения `Decimal` типом объекта в объект типа integer, помечаются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="2de1b-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="2de1b-117">Для создания предупреждения для неявных сужающих преобразований типа, используйте `/optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="2de1b-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="2de1b-118">Используйте `/nowarn:numberlist` игнорировать определенных предупреждений и `/warnaserror:numberlist` обрабатывать конкретного предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="2de1b-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="2de1b-119">Чтобы задать дополнительные сведения в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2de1b-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="2de1b-120">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="2de1b-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2de1b-121">На **проекта** меню, нажмите кнопку **свойства.**</span><span class="sxs-lookup"><span data-stu-id="2de1b-121">On the **Project** menu, click **Properties.**</span></span> <span data-ttu-id="2de1b-122">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="2de1b-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="2de1b-123">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="2de1b-123">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="2de1b-124">Измените значение в **Option Strict** поле.</span><span class="sxs-lookup"><span data-stu-id="2de1b-124">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="2de1b-125">Чтобы установить/optionstrict программными средствами</span><span class="sxs-lookup"><span data-stu-id="2de1b-125">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="2de1b-126">В разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2de1b-126">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2de1b-127">Пример</span><span class="sxs-lookup"><span data-stu-id="2de1b-127">Example</span></span>  
 <span data-ttu-id="2de1b-128">Следующий код компилирует `Test.vb` с помощью строгой семантики.</span><span class="sxs-lookup"><span data-stu-id="2de1b-128">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2de1b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2de1b-129">See Also</span></span>  
 [<span data-ttu-id="2de1b-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2de1b-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2de1b-131">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="2de1b-131">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="2de1b-132">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="2de1b-132">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="2de1b-133">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="2de1b-133">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="2de1b-134">/nowarn</span><span class="sxs-lookup"><span data-stu-id="2de1b-134">/nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [<span data-ttu-id="2de1b-135">/ warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2de1b-135">/warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [<span data-ttu-id="2de1b-136">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2de1b-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="2de1b-137">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="2de1b-137">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="2de1b-138">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="2de1b-138">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
