---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828216"
---
# <a name="-nowarn"></a><span data-ttu-id="0f43e-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="0f43e-102">-nowarn</span></span>
<span data-ttu-id="0f43e-103">Отключает возможность компилятора создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0f43e-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f43e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f43e-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f43e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0f43e-105">Arguments</span></span>  
  
|<span data-ttu-id="0f43e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0f43e-106">Term</span></span>|<span data-ttu-id="0f43e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0f43e-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="0f43e-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="0f43e-108">Optional.</span></span> <span data-ttu-id="0f43e-109">Разделенный запятыми список номеров предупреждений идентификатор, который компилятор не должен отображать.</span><span class="sxs-lookup"><span data-stu-id="0f43e-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="0f43e-110">Если идентификаторы предупреждений не указаны, подавляются все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0f43e-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f43e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f43e-111">Remarks</span></span>  
 <span data-ttu-id="0f43e-112">`-nowarn` Предписывает компилятору не создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0f43e-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="0f43e-113">Чтобы подавить предупреждение об отдельных, укажите идентификатор предупреждения для `-nowarn` после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="0f43e-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="0f43e-114">Разделяйте предупреждения запятыми.</span><span class="sxs-lookup"><span data-stu-id="0f43e-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="0f43e-115">Необходимо указать только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0f43e-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="0f43e-116">Например, если вы хотите отключить BC42024, предупреждение для неиспользуемые локальные переменные, укажите `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="0f43e-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="0f43e-117">Дополнительные сведения об Идентификационных номеров предупреждений, см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0f43e-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="0f43e-118">Чтобы задать - nowarn в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0f43e-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0f43e-119">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="0f43e-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0f43e-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0f43e-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0f43e-121">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="0f43e-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0f43e-122">3.  Выберите **выключить все предупреждения** флажок, чтобы отключить все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0f43e-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="0f43e-123">-или-</span><span class="sxs-lookup"><span data-stu-id="0f43e-123">- or -</span></span><br />     <span data-ttu-id="0f43e-124">Чтобы отключить конкретного предупреждения, щелкните **None** из раскрывающегося списка рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="0f43e-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0f43e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0f43e-125">Example</span></span>  
 <span data-ttu-id="0f43e-126">Следующий код компилирует `T2.vb` и не отображает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0f43e-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="0f43e-127">Пример</span><span class="sxs-lookup"><span data-stu-id="0f43e-127">Example</span></span>  
 <span data-ttu-id="0f43e-128">Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемые локальные переменные (42024).</span><span class="sxs-lookup"><span data-stu-id="0f43e-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f43e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0f43e-129">See also</span></span>

- [<span data-ttu-id="0f43e-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0f43e-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0f43e-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0f43e-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="0f43e-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f43e-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
