---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: c06326a250fba0de2f63e13672b4fffbfa8a07f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796179"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="ba94a-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba94a-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="ba94a-103">Приводит к тому, что компилятор обрабатывает первое появление предупреждения как ошибку.</span><span class="sxs-lookup"><span data-stu-id="ba94a-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba94a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba94a-104">Syntax</span></span>  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba94a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ba94a-105">Arguments</span></span>  
  
|<span data-ttu-id="ba94a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ba94a-106">Term</span></span>|<span data-ttu-id="ba94a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ba94a-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="ba94a-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="ba94a-108">+ &#124; -</span></span>|<span data-ttu-id="ba94a-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ba94a-109">Optional.</span></span> <span data-ttu-id="ba94a-110">Параметр `-warnaserror-` включен по умолчанию. Предупреждения не препятствуют созданию выходного файла компилятором.</span><span class="sxs-lookup"><span data-stu-id="ba94a-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="ba94a-111">Если задан параметр `-warnaserror` или эквивалентный ему `-warnaserror+`, все предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="ba94a-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="ba94a-112">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ba94a-112">Optional.</span></span> <span data-ttu-id="ba94a-113">Разделенный запятыми список с номерами идентификаторов предупреждений, к которому применим параметр `-warnaserror`.</span><span class="sxs-lookup"><span data-stu-id="ba94a-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="ba94a-114">Если идентификатор предупреждения не указан, параметр `-warnaserror` применяется ко всем предупреждениям.</span><span class="sxs-lookup"><span data-stu-id="ba94a-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba94a-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba94a-115">Remarks</span></span>  
 <span data-ttu-id="ba94a-116">Параметр `-warnaserror` обрабатывает все предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="ba94a-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="ba94a-117">Все сообщения, которые до этого получали статус предупреждений, будут возвращаться как ошибки.</span><span class="sxs-lookup"><span data-stu-id="ba94a-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="ba94a-118">Компилятор сообщает о последующих появлениях того же предупреждения как о предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="ba94a-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="ba94a-119">Параметр `-warnaserror-` включен по умолчанию, в результате чего предупреждения имеют только информационный характер.</span><span class="sxs-lookup"><span data-stu-id="ba94a-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="ba94a-120">Если задан параметр `-warnaserror` или эквивалентный ему `-warnaserror+`, все предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="ba94a-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="ba94a-121">Если требуется обрабатывать как ошибки только конкретные предупреждения, укажите их номера через запятую.</span><span class="sxs-lookup"><span data-stu-id="ba94a-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba94a-122">Параметр `-warnaserror` не управляет способом отображения предупреждений.</span><span class="sxs-lookup"><span data-stu-id="ba94a-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="ba94a-123">Используйте параметр [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md), чтобы отключить предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ba94a-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="ba94a-124">Настройка параметра -warnaserror для обработки всех предупреждений как ошибок в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ba94a-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ba94a-125">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ba94a-126">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ba94a-127">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ba94a-128">3.  Убедитесь, что флажок **Выключить все предупреждения** снят.</span><span class="sxs-lookup"><span data-stu-id="ba94a-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="ba94a-129">4.  Проверьте флажок **Обрабатывать все предупреждения как ошибки**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="ba94a-130">Настройка параметра -warnaserror для обработки конкретных предупреждений как ошибок в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ba94a-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ba94a-131">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ba94a-132">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="ba94a-133">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="ba94a-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ba94a-134">3.  Убедитесь, что флажок **Выключить все предупреждения** снят.</span><span class="sxs-lookup"><span data-stu-id="ba94a-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="ba94a-135">4.  Убедитесь, что флажок **Обрабатывать все предупреждения как ошибки** снят.</span><span class="sxs-lookup"><span data-stu-id="ba94a-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="ba94a-136">5.  Выберите **Ошибка** в столбце **Уведомления** рядом с предупреждением, которое должно обрабатываться как ошибка.</span><span class="sxs-lookup"><span data-stu-id="ba94a-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ba94a-137">Пример</span><span class="sxs-lookup"><span data-stu-id="ba94a-137">Example</span></span>  
 <span data-ttu-id="ba94a-138">Следующий код компилирует `In.vb` и настраивает компилятор на отображение ошибки при первом появлении каждого обнаруженного предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ba94a-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="ba94a-139">Пример</span><span class="sxs-lookup"><span data-stu-id="ba94a-139">Example</span></span>  
 <span data-ttu-id="ba94a-140">Следующий код компилирует `T2.vb` и обрабатывает как ошибку только предупреждение о неиспользуемых локальных переменных (42024).</span><span class="sxs-lookup"><span data-stu-id="ba94a-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba94a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ba94a-141">See also</span></span>

- [<span data-ttu-id="ba94a-142">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ba94a-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ba94a-143">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ba94a-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ba94a-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba94a-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
