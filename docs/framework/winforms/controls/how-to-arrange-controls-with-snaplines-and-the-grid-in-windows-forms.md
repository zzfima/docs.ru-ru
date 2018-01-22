---
title: "Практическое руководство. Упорядочение элементов управления с помощью линий привязки и сетки в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 166ccba959bd9facb8e24d580d47577a0c8746a8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="f9d9e-102">Практическое руководство. Упорядочение элементов управления с помощью линий привязки и сетки в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="f9d9e-103">С помощью возможности макета элемента [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно точно указать расположение элементов управления на форме.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-103">Using the layout features of [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="f9d9e-104">Элементы управления, добавляемых на форму или перемещен в форме автоматически выравниваются в строки и столбцы сетки в конструкторе Windows Forms, или можно выравнивать элементы управления с помощью линий привязки.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9d9e-105">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f9d9e-106">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="f9d9e-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f9d9e-107">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f9d9e-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="f9d9e-108">Чтобы привязать все элементы управления к сетке</span><span class="sxs-lookup"><span data-stu-id="f9d9e-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="f9d9e-109">Выберите **SnapToGrid** режим макета в конструкторе Windows Forms **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="f9d9e-110">Дополнительные сведения см. в разделе [Общие, конструктор Windows Forms, диалоговое окно «Параметры»](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span><span class="sxs-lookup"><span data-stu-id="f9d9e-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="f9d9e-111">Теперь все элементы управления выравниваются автоматически по точкам сетки.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="f9d9e-112">Можно привязать отдельные элементы управления к сетке путем блокировки их на месте.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="f9d9e-113">Тем не менее пока они будут заблокированы, их нельзя переместить или изменения размера.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="f9d9e-114">Дополнительные сведения о блокировке элементов управления см. в разделе [как: блокировать элементы управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f9d9e-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="f9d9e-115">Для выравнивания элементов управления с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="f9d9e-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="f9d9e-116">Выберите **линии привязки** режим макета в конструкторе Windows Forms **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="f9d9e-117">Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="f9d9e-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="f9d9e-118">Теперь можно использовать линии привязки для выравнивания и упорядочения элементов управления в форме.</span><span class="sxs-lookup"><span data-stu-id="f9d9e-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d9e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d9e-119">See Also</span></span>  
 [<span data-ttu-id="f9d9e-120">Общие, конструктор Windows Forms, диалоговое окно «Параметры»</span><span class="sxs-lookup"><span data-stu-id="f9d9e-120">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="f9d9e-121">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="f9d9e-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="f9d9e-122">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="f9d9e-123">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="f9d9e-124">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="f9d9e-125">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="f9d9e-126">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="f9d9e-127">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9d9e-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
