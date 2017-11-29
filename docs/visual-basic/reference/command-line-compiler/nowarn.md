---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8da27ea2f9f0a4d370928d70cda1a796b822d97c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nowarn"></a><span data-ttu-id="c09b0-102">/nowarn</span><span class="sxs-lookup"><span data-stu-id="c09b0-102">/nowarn</span></span>
<span data-ttu-id="c09b0-103">Отключает возможность компилятора создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c09b0-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c09b0-104">Syntax</span></span>  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c09b0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c09b0-105">Arguments</span></span>  
  
|<span data-ttu-id="c09b0-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c09b0-106">Term</span></span>|<span data-ttu-id="c09b0-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c09b0-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="c09b0-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="c09b0-108">Optional.</span></span> <span data-ttu-id="c09b0-109">Список с разделителями запятыми Идентификационных номеров предупреждений, компилятор не должен отображать.</span><span class="sxs-lookup"><span data-stu-id="c09b0-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="c09b0-110">Если идентификаторы предупреждений не указаны, то все предупреждения подавляются.</span><span class="sxs-lookup"><span data-stu-id="c09b0-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c09b0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c09b0-111">Remarks</span></span>  
 <span data-ttu-id="c09b0-112">`/nowarn` Заставляет компилятор не создает предупреждений.</span><span class="sxs-lookup"><span data-stu-id="c09b0-112">The `/nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="c09b0-113">Для подавления отдельных предупреждений, укажите идентификатор предупреждения для `/nowarn` после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="c09b0-113">To suppress an individual warning, supply the warning ID to the `/nowarn` option following the colon.</span></span> <span data-ttu-id="c09b0-114">Несколько номеров предупреждений следует разделяйте запятыми.</span><span class="sxs-lookup"><span data-stu-id="c09b0-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="c09b0-115">Необходимо указать числовой частью идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c09b0-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="c09b0-116">Например, если вы хотите запретить BC42024, предупреждение для неиспользуемых локальных переменных, указать `/nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="c09b0-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `/nowarn:42024`.</span></span>  
  
 <span data-ttu-id="c09b0-117">Дополнительные сведения о Идентификационных номеров предупреждений см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c09b0-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="c09b0-118">Установка в Visual Studio/nowarn интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="c09b0-118">To set /nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c09b0-119">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c09b0-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c09b0-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c09b0-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="c09b0-121">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="c09b0-121">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="c09b0-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c09b0-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c09b0-123">3.  Выберите **отключить все предупреждения** флажок, чтобы отключить все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c09b0-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="c09b0-124">-или-</span><span class="sxs-lookup"><span data-stu-id="c09b0-124">- or -</span></span><br />     <span data-ttu-id="c09b0-125">Чтобы отключить конкретного предупреждения, щелкните **нет** из раскрывающегося списка рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="c09b0-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c09b0-126">Пример</span><span class="sxs-lookup"><span data-stu-id="c09b0-126">Example</span></span>  
 <span data-ttu-id="c09b0-127">Следующий код компилирует `T2.vb` и не отображает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c09b0-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="c09b0-128">Пример</span><span class="sxs-lookup"><span data-stu-id="c09b0-128">Example</span></span>  
 <span data-ttu-id="c09b0-129">Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).</span><span class="sxs-lookup"><span data-stu-id="c09b0-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c09b0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c09b0-130">See Also</span></span>  
 [<span data-ttu-id="c09b0-131">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c09b0-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c09b0-132">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c09b0-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c09b0-133">Настройка предупреждений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c09b0-133">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
