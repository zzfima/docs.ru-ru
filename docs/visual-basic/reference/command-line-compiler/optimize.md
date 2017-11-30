---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a><span data-ttu-id="409f8-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="409f8-102">/optimize</span></span>
<span data-ttu-id="409f8-103">Включает или отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="409f8-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="409f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="409f8-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="409f8-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="409f8-105">Arguments</span></span>  
  
|<span data-ttu-id="409f8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="409f8-106">Term</span></span>|<span data-ttu-id="409f8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="409f8-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="409f8-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="409f8-108">`+` &#124; `-`</span></span>|<span data-ttu-id="409f8-109">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="409f8-109">Optional.</span></span> <span data-ttu-id="409f8-110">`/optimize-` Отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="409f8-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="409f8-111">`/optimize+` Включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="409f8-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="409f8-112">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="409f8-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="409f8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="409f8-113">Remarks</span></span>  
 <span data-ttu-id="409f8-114">Оптимизации компилятора делают код более быстрым, коротким и эффективным.</span><span class="sxs-lookup"><span data-stu-id="409f8-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="409f8-115">Тем не менее, поскольку оптимизации привести изменения порядка строк кода `/optimize+` может осложнить процесс отладки.</span><span class="sxs-lookup"><span data-stu-id="409f8-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="409f8-116">Все модули, созданные с помощью `/target:module` для сборки должны использовать одинаковые `/optimize` параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="409f8-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="409f8-117">Дополнительные сведения см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="409f8-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="409f8-118">Можно объединять `/optimize` и `/debug` параметры.</span><span class="sxs-lookup"><span data-stu-id="409f8-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="409f8-119">Чтобы установить параметр / optimize в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="409f8-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="409f8-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="409f8-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="409f8-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="409f8-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="409f8-122">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="409f8-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="409f8-123">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="409f8-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="409f8-124">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="409f8-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="409f8-125">4.  Изменить **включить оптимизацию** флажок.</span><span class="sxs-lookup"><span data-stu-id="409f8-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="409f8-126">Пример</span><span class="sxs-lookup"><span data-stu-id="409f8-126">Example</span></span>  
 <span data-ttu-id="409f8-127">Следующий код компилирует `T2.vb` и включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="409f8-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="409f8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="409f8-128">See Also</span></span>  
 [<span data-ttu-id="409f8-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="409f8-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="409f8-130">/ Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="409f8-130">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="409f8-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="409f8-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="409f8-132">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="409f8-132">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
