---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336087"
---
# <a name="-optionstrict"></a><span data-ttu-id="cbc84-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="cbc84-102">-optionstrict</span></span>
<span data-ttu-id="cbc84-103">Требовать строгой семантики для ограничения неявного преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="cbc84-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbc84-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cbc84-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cbc84-105">Arguments</span></span>  
 <span data-ttu-id="cbc84-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="cbc84-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="cbc84-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cbc84-107">Optional.</span></span> <span data-ttu-id="cbc84-108">`-optionstrict+` Ограничивает неявное преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="cbc84-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="cbc84-109">Значение по умолчанию для этого параметра — `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="cbc84-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="cbc84-110">`-optionstrict+` Параметр совпадает со значением `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="cbc84-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="cbc84-111">Можно использовать как для разрешающей семантики.</span><span class="sxs-lookup"><span data-stu-id="cbc84-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="cbc84-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cbc84-112">Required.</span></span> <span data-ttu-id="cbc84-113">Предупреждать, когда не накладывается ограничение на строгую семантику языка.</span><span class="sxs-lookup"><span data-stu-id="cbc84-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbc84-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbc84-114">Remarks</span></span>  
 <span data-ttu-id="cbc84-115">Когда `-optionstrict+` по сути, является неявно могут выполняться только расширяющие преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="cbc84-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="cbc84-116">Неявные преобразования типов, например назначение `Decimal` введите в объект типа integer, которые выводятся как ошибки.</span><span class="sxs-lookup"><span data-stu-id="cbc84-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="cbc84-117">Чтобы создать предупреждения для неявных сужающих преобразований типа, используйте `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="cbc84-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="cbc84-118">Используйте `-nowarn:numberlist` для игнорирования определенных предупреждений и `-warnaserror:numberlist` для конкретного предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="cbc84-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="cbc84-119">Чтобы задать - optionstrict в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cbc84-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="cbc84-120">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="cbc84-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cbc84-121">На **проекта** меню, щелкните **свойства.**</span><span class="sxs-lookup"><span data-stu-id="cbc84-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="cbc84-122">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="cbc84-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="cbc84-123">Измените значение в **Option Strict** поле.</span><span class="sxs-lookup"><span data-stu-id="cbc84-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="cbc84-124">Чтобы установить - optionstrict программными средствами</span><span class="sxs-lookup"><span data-stu-id="cbc84-124">To set -optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="cbc84-125">См. в разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cbc84-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc84-126">Пример</span><span class="sxs-lookup"><span data-stu-id="cbc84-126">Example</span></span>  
 <span data-ttu-id="cbc84-127">Следующий код компилирует `Test.vb` с помощью строгой семантики.</span><span class="sxs-lookup"><span data-stu-id="cbc84-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbc84-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc84-128">See also</span></span>

- [<span data-ttu-id="cbc84-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="cbc84-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cbc84-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="cbc84-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="cbc84-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="cbc84-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="cbc84-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="cbc84-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="cbc84-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="cbc84-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="cbc84-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc84-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="cbc84-135">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="cbc84-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="cbc84-136">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="cbc84-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="cbc84-137">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="cbc84-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
