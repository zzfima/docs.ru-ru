---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ae8ed68045529e626f2788f854d8e6a6933e7e2
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="0a72f-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a72f-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="0a72f-103">Указывает компилятору на необходимость рассматривает первое вхождение предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a72f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a72f-104">Syntax</span></span>  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0a72f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0a72f-105">Arguments</span></span>  
  
|<span data-ttu-id="0a72f-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0a72f-106">Term</span></span>|<span data-ttu-id="0a72f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0a72f-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0a72f-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="0a72f-108">+ &#124; -</span></span>|<span data-ttu-id="0a72f-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0a72f-109">Optional.</span></span> <span data-ttu-id="0a72f-110">По умолчанию `-warnaserror-` — действует; предупреждения не мешают компилятор создает выходной файл.</span><span class="sxs-lookup"><span data-stu-id="0a72f-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="0a72f-111">`-warnaserror` Параметр, так как `-warnaserror+`, предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="0a72f-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0a72f-112">Optional.</span></span> <span data-ttu-id="0a72f-113">Разделенный запятыми список идентификаторов предупреждений номеров, к которому `-warnaserror` применяется параметр.</span><span class="sxs-lookup"><span data-stu-id="0a72f-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="0a72f-114">Если идентификатор предупреждения не указан, `-warnaserror` параметр применяется ко всем предупреждениям.</span><span class="sxs-lookup"><span data-stu-id="0a72f-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a72f-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a72f-115">Remarks</span></span>  
 <span data-ttu-id="0a72f-116">`-warnaserror` Обрабатывает все предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="0a72f-117">Все сообщения, которые обычно рассматриваются как предупреждения, выводятся как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="0a72f-118">Компилятор сообщает следующих вхождений того же предупреждения как предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0a72f-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="0a72f-119">По умолчанию `-warnaserror-` , в результате чего предупреждения только в информационных целях.</span><span class="sxs-lookup"><span data-stu-id="0a72f-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="0a72f-120">`-warnaserror` Параметр, так как `-warnaserror+`, предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="0a72f-121">Если требуется только несколько определенных предупреждений, которые обрабатываются как ошибки, можно указать запятыми список номеров предупреждений, обрабатываемых как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a72f-122">`-warnaserror` Не управляет способом отображения предупреждений.</span><span class="sxs-lookup"><span data-stu-id="0a72f-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="0a72f-123">Используйте [- nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) параметр, чтобы отключить предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0a72f-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="0a72f-124">Чтобы задать - warnaserror обрабатывать все предупреждения как ошибки в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a72f-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0a72f-125">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0a72f-126">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0a72f-127">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0a72f-128">3.  Убедитесь, что **отключить все предупреждения** флажок снят.</span><span class="sxs-lookup"><span data-stu-id="0a72f-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="0a72f-129">4.  Проверьте **обрабатывать все предупреждения как ошибки** флажок.</span><span class="sxs-lookup"><span data-stu-id="0a72f-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="0a72f-130">Чтобы задать - warnaserror обрабатывать предупреждения как ошибки в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a72f-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0a72f-131">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0a72f-132">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="0a72f-133">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0a72f-134">3.  Убедитесь, что **отключить все предупреждения** флажок снят.</span><span class="sxs-lookup"><span data-stu-id="0a72f-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="0a72f-135">4.  Убедитесь, что **обрабатывать все предупреждения как ошибки** флажок снят.</span><span class="sxs-lookup"><span data-stu-id="0a72f-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="0a72f-136">5.  Выберите **ошибка** из **уведомления** столбец рядом с предупреждением, которое должно обрабатываться как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a72f-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0a72f-137">Пример</span><span class="sxs-lookup"><span data-stu-id="0a72f-137">Example</span></span>  
 <span data-ttu-id="0a72f-138">Следующий код компилирует `In.vb` , а компилятор отображает ошибку для первого вхождения каждого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0a72f-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="0a72f-139">Пример</span><span class="sxs-lookup"><span data-stu-id="0a72f-139">Example</span></span>  
 <span data-ttu-id="0a72f-140">Следующий код компилирует `T2.vb` и обрабатывает только предупреждения для неиспользуемых локальных переменных (42024) как ошибку.</span><span class="sxs-lookup"><span data-stu-id="0a72f-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a72f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="0a72f-141">See Also</span></span>  
 [<span data-ttu-id="0a72f-142">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0a72f-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0a72f-143">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0a72f-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="0a72f-144">Настройка предупреждений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a72f-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
