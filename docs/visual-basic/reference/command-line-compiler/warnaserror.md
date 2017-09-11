---
title: "/ warnaserror (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
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
ms.openlocfilehash: 8ed72415a75860b34e37c2bf4fc686cdae37f69e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="50708-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50708-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="50708-103">Указывает компилятору обрабатывать первое предупреждение как ошибку.</span><span class="sxs-lookup"><span data-stu-id="50708-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50708-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50708-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="50708-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="50708-105">Arguments</span></span>  
  
|<span data-ttu-id="50708-106">Термин</span><span class="sxs-lookup"><span data-stu-id="50708-106">Term</span></span>|<span data-ttu-id="50708-107">Определение</span><span class="sxs-lookup"><span data-stu-id="50708-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="50708-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="50708-108">+ &#124; -</span></span>|<span data-ttu-id="50708-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="50708-109">Optional.</span></span> <span data-ttu-id="50708-110">По умолчанию `/warnaserror-` — фактически; предупреждения не запретить компилятору создавать выходной файл.</span><span class="sxs-lookup"><span data-stu-id="50708-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="50708-111">`/warnaserror` Вариант, который одинаков как `/warnaserror+`, предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="50708-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="50708-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="50708-112">Optional.</span></span> <span data-ttu-id="50708-113">Разделенный запятыми список идентификаторов предупреждений числа, к которому `/warnaserror` применяется параметр.</span><span class="sxs-lookup"><span data-stu-id="50708-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="50708-114">Если идентификатор предупреждения не указан, `/warnaserror` параметр применяется ко всем предупреждениям.</span><span class="sxs-lookup"><span data-stu-id="50708-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50708-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="50708-115">Remarks</span></span>  
 <span data-ttu-id="50708-116">`/warnaserror` Обрабатывает все предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="50708-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="50708-117">Все сообщения, которые обычно рассматриваются как предупреждения, выводятся как ошибки.</span><span class="sxs-lookup"><span data-stu-id="50708-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="50708-118">Компилятор сообщает следующие вхождения того же предупреждения как предупреждения.</span><span class="sxs-lookup"><span data-stu-id="50708-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="50708-119">По умолчанию `/warnaserror-` , в результате чего предупреждения только в информационных целях.</span><span class="sxs-lookup"><span data-stu-id="50708-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="50708-120">`/warnaserror` Вариант, который одинаков как `/warnaserror+`, предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="50708-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="50708-121">Если требуется только несколько определенных предупреждений, которые обрабатываются как ошибки, можно указать разделенный запятыми список номеров предупреждений, которые следует обрабатывать как ошибки.</span><span class="sxs-lookup"><span data-stu-id="50708-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50708-122">`/warnaserror` Не управляет способом отображения предупреждений.</span><span class="sxs-lookup"><span data-stu-id="50708-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="50708-123">Используйте [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) параметр, чтобы отключить предупреждения.</span><span class="sxs-lookup"><span data-stu-id="50708-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="50708-124">Установка параметра/warnaserror для обработки всех предупреждений как ошибок в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="50708-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="50708-125">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="50708-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="50708-126">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="50708-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="50708-127">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="50708-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="50708-128">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="50708-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="50708-129">3.  Убедитесь, что **отключить все предупреждения** флажок снят.</span><span class="sxs-lookup"><span data-stu-id="50708-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="50708-130">4.  Проверьте **обрабатывать все предупреждения как ошибки** флажок.</span><span class="sxs-lookup"><span data-stu-id="50708-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="50708-131">Установка параметра/warnaserror для обработки выбранных предупреждений как ошибок в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="50708-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="50708-132">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="50708-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="50708-133">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="50708-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="50708-134">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="50708-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="50708-135">3.  Убедитесь, что **отключить все предупреждения** флажок снят.</span><span class="sxs-lookup"><span data-stu-id="50708-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="50708-136">4.  Убедитесь, что **обрабатывать все предупреждения как ошибки** флажок снят.</span><span class="sxs-lookup"><span data-stu-id="50708-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="50708-137">5.  Выберите **ошибка** из **уведомления** столбец рядом с предупреждением, которое должно обрабатываться как ошибки.</span><span class="sxs-lookup"><span data-stu-id="50708-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="50708-138">Пример</span><span class="sxs-lookup"><span data-stu-id="50708-138">Example</span></span>  
 <span data-ttu-id="50708-139">Следующий код компилирует `In.vb` , а компилятор отображает ошибку для первого вхождения каждого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="50708-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="50708-140">Пример</span><span class="sxs-lookup"><span data-stu-id="50708-140">Example</span></span>  
 <span data-ttu-id="50708-141">Следующий код компилирует `T2.vb` и обрабатывает только предупреждения для неиспользуемых локальных переменных (42024) как ошибка.</span><span class="sxs-lookup"><span data-stu-id="50708-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="50708-142">См. также</span><span class="sxs-lookup"><span data-stu-id="50708-142">See Also</span></span>  
 <span data-ttu-id="50708-143">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="50708-143">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="50708-144"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="50708-144"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="50708-145"> [Настройка предупреждений в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="50708-145"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
