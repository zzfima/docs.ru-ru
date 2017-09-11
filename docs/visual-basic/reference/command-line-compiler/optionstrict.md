---
title: "/ optionstrict | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
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
ms.openlocfilehash: c22445cb53ca4f5621cf7aa69ab840b26f8e08c9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="optionstrict"></a><span data-ttu-id="73723-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="73723-102">/optionstrict</span></span>
<span data-ttu-id="73723-103">Требовать строгой семантики для ограничения неявного преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="73723-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73723-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73723-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="73723-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="73723-105">Arguments</span></span>  
 <span data-ttu-id="73723-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="73723-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="73723-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="73723-107">Optional.</span></span> <span data-ttu-id="73723-108">`/optionstrict+` Ограничивает неявное преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="73723-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="73723-109">Значение по умолчанию для этого параметра — `/optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="73723-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="73723-110">`/optionstrict+` Действует так же, как `/optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="73723-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="73723-111">Можно использовать как для разрешающей семантики.</span><span class="sxs-lookup"><span data-stu-id="73723-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="73723-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="73723-112">Required.</span></span> <span data-ttu-id="73723-113">Предупреждать, когда не накладывается ограничение на строгую семантику языка.</span><span class="sxs-lookup"><span data-stu-id="73723-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73723-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="73723-114">Remarks</span></span>  
 <span data-ttu-id="73723-115">Когда `/optionstrict+` действует, неявно могут выполняться только расширяющие преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="73723-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="73723-116">Неявные преобразования типов, например для присвоения `Decimal` тип объекта в объект типа integer, выводятся как ошибки.</span><span class="sxs-lookup"><span data-stu-id="73723-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="73723-117">Чтобы создать предупреждения для неявных сужающих преобразований типа, используйте `/optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="73723-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="73723-118">Используйте `/nowarn:numberlist` пропускать определенных предупреждений и `/warnaserror:numberlist` рассматривать конкретного предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="73723-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="73723-119">Чтобы задать дополнительные сведения в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73723-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="73723-120">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="73723-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73723-121">На **проекта** меню, щелкните **свойства.**</span><span class="sxs-lookup"><span data-stu-id="73723-121">On the **Project** menu, click **Properties.**</span></span> <span data-ttu-id="73723-122">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="73723-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="73723-123">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="73723-123">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="73723-124">Измените значение в **Option Strict** поле.</span><span class="sxs-lookup"><span data-stu-id="73723-124">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="73723-125">Чтобы установить/optionstrict программными средствами</span><span class="sxs-lookup"><span data-stu-id="73723-125">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="73723-126">В разделе [Option Strict оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73723-126">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73723-127">Пример</span><span class="sxs-lookup"><span data-stu-id="73723-127">Example</span></span>  
 <span data-ttu-id="73723-128">Следующий код компилирует `Test.vb` с помощью строгой семантики.</span><span class="sxs-lookup"><span data-stu-id="73723-128">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="73723-129">См. также</span><span class="sxs-lookup"><span data-stu-id="73723-129">See Also</span></span>  
 <span data-ttu-id="73723-130">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="73723-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="73723-131"> [Дополнительные](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="73723-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="73723-132"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="73723-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="73723-133"> [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="73723-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="73723-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span><span class="sxs-lookup"><span data-stu-id="73723-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span></span>  
<span data-ttu-id="73723-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span><span class="sxs-lookup"><span data-stu-id="73723-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span></span>  
<span data-ttu-id="73723-136"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="73723-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="73723-137"> [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="73723-137"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="73723-138"> [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="73723-138"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
