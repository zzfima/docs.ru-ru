---
title: -Оптимизация
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7df1c873c166def9fde1bedc139470263e3e4437
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-optimize"></a><span data-ttu-id="c5c17-102">-Оптимизация</span><span class="sxs-lookup"><span data-stu-id="c5c17-102">-optimize</span></span>
<span data-ttu-id="c5c17-103">Включает или отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="c5c17-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c17-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5c17-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5c17-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c5c17-105">Arguments</span></span>  
  
|<span data-ttu-id="c5c17-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c5c17-106">Term</span></span>|<span data-ttu-id="c5c17-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c5c17-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c5c17-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c5c17-108">`+` &#124; `-`</span></span>|<span data-ttu-id="c5c17-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5c17-109">Optional.</span></span> <span data-ttu-id="c5c17-110">`-optimize-` Отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="c5c17-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="c5c17-111">`-optimize+` Включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="c5c17-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="c5c17-112">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="c5c17-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5c17-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5c17-113">Remarks</span></span>  
 <span data-ttu-id="c5c17-114">Оптимизации компилятора делают код более быстрым, коротким и эффективным.</span><span class="sxs-lookup"><span data-stu-id="c5c17-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="c5c17-115">Тем не менее, поскольку оптимизации привести изменения порядка строк кода `-optimize+` может осложнить процесс отладки.</span><span class="sxs-lookup"><span data-stu-id="c5c17-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="c5c17-116">Все модули, созданные с помощью `-target:module` для сборки должны использовать одинаковые `-optimize` параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="c5c17-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="c5c17-117">Дополнительные сведения см. в разделе [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="c5c17-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="c5c17-118">Можно объединять `-optimize` и `-debug` параметры.</span><span class="sxs-lookup"><span data-stu-id="c5c17-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="c5c17-119">Чтобы задать - оптимизации в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c5c17-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c5c17-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c5c17-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="c5c17-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c5c17-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c5c17-123">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="c5c17-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="c5c17-124">4.  Изменить **включить оптимизацию** флажок.</span><span class="sxs-lookup"><span data-stu-id="c5c17-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5c17-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c5c17-125">Example</span></span>  
 <span data-ttu-id="c5c17-126">Следующий код компилирует `T2.vb` и включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="c5c17-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5c17-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c5c17-127">See Also</span></span>  
 [<span data-ttu-id="c5c17-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c5c17-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c5c17-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5c17-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="c5c17-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c5c17-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c5c17-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5c17-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
