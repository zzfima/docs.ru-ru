---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 338b4672d215968275c30d37a2f8061e764aed8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-nowarn"></a><span data-ttu-id="d7c8b-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="d7c8b-102">-nowarn</span></span>
<span data-ttu-id="d7c8b-103">Отключает возможность компилятора создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7c8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7c8b-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7c8b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d7c8b-105">Arguments</span></span>  
  
|<span data-ttu-id="d7c8b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="d7c8b-106">Term</span></span>|<span data-ttu-id="d7c8b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="d7c8b-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="d7c8b-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-108">Optional.</span></span> <span data-ttu-id="d7c8b-109">Список с разделителями запятыми Идентификационных номеров предупреждений, компилятор не должен отображать.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="d7c8b-110">Если идентификаторы предупреждений не указаны, то все предупреждения подавляются.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7c8b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7c8b-111">Remarks</span></span>  
 <span data-ttu-id="d7c8b-112">`-nowarn` Заставляет компилятор не создает предупреждений.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="d7c8b-113">Для подавления отдельных предупреждений, укажите идентификатор предупреждения для `-nowarn` после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="d7c8b-114">Несколько номеров предупреждений следует разделяйте запятыми.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="d7c8b-115">Необходимо указать числовой частью идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="d7c8b-116">Например, если вы хотите запретить BC42024, предупреждение для неиспользуемых локальных переменных, указать `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="d7c8b-117">Дополнительные сведения о Идентификационных номеров предупреждений см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d7c8b-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="d7c8b-118">Чтобы задать - nowarn в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7c8b-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d7c8b-119">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d7c8b-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d7c8b-121">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d7c8b-122">3.  Выберите **отключить все предупреждения** флажок, чтобы отключить все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="d7c8b-123">-или-</span><span class="sxs-lookup"><span data-stu-id="d7c8b-123">- or -</span></span><br />     <span data-ttu-id="d7c8b-124">Чтобы отключить конкретного предупреждения, щелкните **нет** из раскрывающегося списка рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d7c8b-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d7c8b-125">Example</span></span>  
 <span data-ttu-id="d7c8b-126">Следующий код компилирует `T2.vb` и не отображает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d7c8b-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="d7c8b-127">Пример</span><span class="sxs-lookup"><span data-stu-id="d7c8b-127">Example</span></span>  
 <span data-ttu-id="d7c8b-128">Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).</span><span class="sxs-lookup"><span data-stu-id="d7c8b-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7c8b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d7c8b-129">See Also</span></span>  
 [<span data-ttu-id="d7c8b-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d7c8b-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d7c8b-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d7c8b-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d7c8b-132">Настройка предупреждений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7c8b-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
