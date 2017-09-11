---
title: "/ optimize | Документы Microsoft"
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
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization, enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
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
ms.openlocfilehash: f01ab17d4a2f5d123538294a7a13d7a6d7a40267
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="optimize"></a><span data-ttu-id="40bed-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="40bed-102">/optimize</span></span>
<span data-ttu-id="40bed-103">Включает или отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="40bed-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40bed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40bed-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="40bed-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="40bed-105">Arguments</span></span>  
  
|<span data-ttu-id="40bed-106">Термин</span><span class="sxs-lookup"><span data-stu-id="40bed-106">Term</span></span>|<span data-ttu-id="40bed-107">Определение</span><span class="sxs-lookup"><span data-stu-id="40bed-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="40bed-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="40bed-108">`+` &#124; `-`</span></span>|<span data-ttu-id="40bed-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="40bed-109">Optional.</span></span> <span data-ttu-id="40bed-110">`/optimize-` Отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="40bed-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="40bed-111">`/optimize+` Включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="40bed-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="40bed-112">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="40bed-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40bed-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="40bed-113">Remarks</span></span>  
 <span data-ttu-id="40bed-114">Оптимизация кода делает выходной файл меньшего размера, быстрее и эффективнее.</span><span class="sxs-lookup"><span data-stu-id="40bed-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="40bed-115">Однако, поскольку изменения порядка строк кода в оптимизации `/optimize+` может осложнить процесс отладки.</span><span class="sxs-lookup"><span data-stu-id="40bed-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="40bed-116">Все модули, созданные с помощью `/target:module` для сборки должны использовать одинаковые `/optimize` параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="40bed-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="40bed-117">Дополнительные сведения см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="40bed-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="40bed-118">Можно объединить `/optimize` и `/debug` параметры.</span><span class="sxs-lookup"><span data-stu-id="40bed-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="40bed-119">Чтобы установить параметр / optimize в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="40bed-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="40bed-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="40bed-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="40bed-121">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="40bed-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="40bed-122">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="40bed-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="40bed-123">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="40bed-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="40bed-124">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="40bed-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="40bed-125">4.  Изменить **включить оптимизацию** флажок.</span><span class="sxs-lookup"><span data-stu-id="40bed-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="40bed-126">Пример</span><span class="sxs-lookup"><span data-stu-id="40bed-126">Example</span></span>  
 <span data-ttu-id="40bed-127">Следующий код компилирует `T2.vb` и включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="40bed-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="40bed-128">См. также</span><span class="sxs-lookup"><span data-stu-id="40bed-128">See Also</span></span>  
 <span data-ttu-id="40bed-129">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="40bed-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="40bed-130"> [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="40bed-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="40bed-131"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="40bed-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="40bed-132"> [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span><span class="sxs-lookup"><span data-stu-id="40bed-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span></span>
