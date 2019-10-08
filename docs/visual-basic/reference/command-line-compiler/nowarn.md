---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005400"
---
# <a name="-nowarn"></a><span data-ttu-id="6e3dd-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="6e3dd-102">-nowarn</span></span>
<span data-ttu-id="6e3dd-103">Отключает возможность компилятора создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e3dd-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e3dd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6e3dd-105">Arguments</span></span>  
  
|<span data-ttu-id="6e3dd-106">Термин</span><span class="sxs-lookup"><span data-stu-id="6e3dd-106">Term</span></span>|<span data-ttu-id="6e3dd-107">Определение</span><span class="sxs-lookup"><span data-stu-id="6e3dd-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="6e3dd-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-108">Optional.</span></span> <span data-ttu-id="6e3dd-109">Разделенный запятыми список ИДЕНТИФИКАЦИОНных номеров предупреждений, которые компилятор должен подавлять.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="6e3dd-110">Если идентификаторы предупреждений не указаны, все предупреждения подавляются.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e3dd-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e3dd-111">Remarks</span></span>  
 <span data-ttu-id="6e3dd-112">Параметр `-nowarn` приводит к тому, что компилятор не создает предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="6e3dd-113">Чтобы отключить отдельное предупреждение, укажите идентификатор предупреждения для параметра `-nowarn` после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="6e3dd-114">Несколько номеров предупреждений разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="6e3dd-115">Необходимо указать только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="6e3dd-116">Например, если вы хотите отключить BC42024, предупреждение для неиспользуемых локальных переменных укажите `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="6e3dd-117">Дополнительные сведения об ИДЕНТИФИКАТОРах предупреждений см. [в разделе Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6e3dd-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="6e3dd-118">Установка параметра-unwarn в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6e3dd-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6e3dd-119">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6e3dd-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6e3dd-121">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6e3dd-122">3.  Установите флажок **Отключить все предупреждения** , чтобы отключить все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="6e3dd-123">-или-</span><span class="sxs-lookup"><span data-stu-id="6e3dd-123">- or -</span></span><br />     <span data-ttu-id="6e3dd-124">Чтобы отключить определенное предупреждение, выберите пункт **нет** в раскрывающемся списке рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6e3dd-125">Пример</span><span class="sxs-lookup"><span data-stu-id="6e3dd-125">Example</span></span>  
 <span data-ttu-id="6e3dd-126">Следующий код компилирует `T2.vb` и не отображает предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6e3dd-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="6e3dd-127">Пример</span><span class="sxs-lookup"><span data-stu-id="6e3dd-127">Example</span></span>  
 <span data-ttu-id="6e3dd-128">Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).</span><span class="sxs-lookup"><span data-stu-id="6e3dd-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e3dd-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6e3dd-129">See also</span></span>

- [<span data-ttu-id="6e3dd-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6e3dd-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6e3dd-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6e3dd-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6e3dd-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e3dd-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
