---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005374"
---
# <a name="-optimize"></a><span data-ttu-id="a9c5b-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="a9c5b-102">-optimize</span></span>
<span data-ttu-id="a9c5b-103">Включает или отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9c5b-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a9c5b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a9c5b-105">Arguments</span></span>  
  
|<span data-ttu-id="a9c5b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="a9c5b-106">Term</span></span>|<span data-ttu-id="a9c5b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="a9c5b-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="a9c5b-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a9c5b-108">`+` &#124; `-`</span></span>|<span data-ttu-id="a9c5b-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-109">Optional.</span></span> <span data-ttu-id="a9c5b-110">Параметр `-optimize-` отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="a9c5b-111">Параметр `-optimize+` включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="a9c5b-112">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c5b-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9c5b-113">Remarks</span></span>  
 <span data-ttu-id="a9c5b-114">Оптимизации компилятора делают код более быстрым, коротким и эффективным.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="a9c5b-115">Однако поскольку оптимизация приводит к перестановке кода в выходном файле, `-optimize+` может усложнить отладку.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="a9c5b-116">Все модули, созданные с `-target:module` для сборки, должны использовать те же параметры `-optimize`, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="a9c5b-117">Дополнительные сведения см. в разделе [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="a9c5b-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="a9c5b-118">Можно сочетать параметры `-optimize` и `-debug`.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="a9c5b-119">Установка параметра-optimize в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a9c5b-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a9c5b-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a9c5b-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="a9c5b-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a9c5b-123">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="a9c5b-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="a9c5b-124">4.  Измените флажок **включить оптимизацию** .</span><span class="sxs-lookup"><span data-stu-id="a9c5b-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9c5b-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a9c5b-125">Example</span></span>  
 <span data-ttu-id="a9c5b-126">Следующий код компилирует `T2.vb` и включает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="a9c5b-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9c5b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a9c5b-127">See also</span></span>

- [<span data-ttu-id="a9c5b-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a9c5b-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a9c5b-129">-Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9c5b-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="a9c5b-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a9c5b-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="a9c5b-131">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9c5b-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
