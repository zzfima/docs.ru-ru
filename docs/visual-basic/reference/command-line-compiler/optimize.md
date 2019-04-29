---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788977"
---
# <a name="-optimize"></a><span data-ttu-id="4e27e-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="4e27e-102">-optimize</span></span>
<span data-ttu-id="4e27e-103">Включает или отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="4e27e-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e27e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e27e-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e27e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4e27e-105">Arguments</span></span>  
  
|<span data-ttu-id="4e27e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4e27e-106">Term</span></span>|<span data-ttu-id="4e27e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4e27e-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="4e27e-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4e27e-108">`+` &#124; `-`</span></span>|<span data-ttu-id="4e27e-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="4e27e-109">Optional.</span></span> <span data-ttu-id="4e27e-110">`-optimize-` Отключает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="4e27e-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="4e27e-111">`-optimize+` Включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="4e27e-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="4e27e-112">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="4e27e-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e27e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e27e-113">Remarks</span></span>  
 <span data-ttu-id="4e27e-114">Оптимизации компилятора делают код более быстрым, коротким и эффективным.</span><span class="sxs-lookup"><span data-stu-id="4e27e-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="4e27e-115">Тем не менее, так как оптимизации изменения порядка строк кода в выходном файле `-optimize+` может осложнить процесс отладки.</span><span class="sxs-lookup"><span data-stu-id="4e27e-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="4e27e-116">Все модули, созданные с помощью `-target:module` для сборки, должны использовать одинаковые `-optimize` параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="4e27e-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="4e27e-117">Дополнительные сведения см. в разделе [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="4e27e-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="4e27e-118">Вы можете объединить `-optimize` и `-debug` параметры.</span><span class="sxs-lookup"><span data-stu-id="4e27e-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="4e27e-119">Чтобы задать - оптимизации в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4e27e-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4e27e-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="4e27e-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4e27e-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e27e-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="4e27e-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="4e27e-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4e27e-123">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="4e27e-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="4e27e-124">4.  Изменить **включить оптимизацию** "флажок".</span><span class="sxs-lookup"><span data-stu-id="4e27e-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4e27e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="4e27e-125">Example</span></span>  
 <span data-ttu-id="4e27e-126">Следующий код компилирует `T2.vb` и включает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="4e27e-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e27e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4e27e-127">See also</span></span>

- [<span data-ttu-id="4e27e-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="4e27e-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4e27e-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e27e-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="4e27e-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="4e27e-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="4e27e-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e27e-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
