---
title: "Элемент управления SplitContainer (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66eb0e8fc630696c86c8b85c85b67023bd568dc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="35177-102">Элемент управления SplitContainer (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="35177-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="35177-103">Элемент управления Windows Forms `SplitContainer` состоит из двух панелей, разделенных подвижной полосой.</span><span class="sxs-lookup"><span data-stu-id="35177-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="35177-104">При наведении указателя мыши на полосу его форма изменяется, показывая, что полоса является перемещаемой.</span><span class="sxs-lookup"><span data-stu-id="35177-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35177-105">В **элементов**, этот элемент управления заменяет <xref:System.Windows.Forms.Splitter> , присутствующий в предыдущей версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="35177-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="35177-106">Элемент управления `SplitContainer` намного предпочтительнее, чем элемент управления <xref:System.Windows.Forms.Splitter>.</span><span class="sxs-lookup"><span data-stu-id="35177-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="35177-107">Класс <xref:System.Windows.Forms.Splitter> по-прежнему имеется в .NET Framework для обеспечения совместимости с существующими приложениями, но для новых проектов настоятельно рекомендуется использовать элемент управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="35177-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="35177-108">С помощью элемента управления `SplitContainer` можно создавать сложные пользовательские интерфейсы. Часто выбор на одной панели определяет объекты, отображаемые на другой.</span><span class="sxs-lookup"><span data-stu-id="35177-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="35177-109">Такой подход является весьма эффективным для отображения и просмотра информации.</span><span class="sxs-lookup"><span data-stu-id="35177-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="35177-110">Две панели позволяют группировать информацию, а полоса или разделитель упрощают изменение размера панелей.</span><span class="sxs-lookup"><span data-stu-id="35177-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35177-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="35177-111">In This Section</span></span>  
 [<span data-ttu-id="35177-112">Общие сведения о компоненте SplitContainer</span><span class="sxs-lookup"><span data-stu-id="35177-112">SplitContainer Control Overview</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="35177-113">Приводятся основные сведения об элементе управления `SplitContainer`, и описываются его часто используемые свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="35177-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="35177-114">Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем</span><span class="sxs-lookup"><span data-stu-id="35177-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="35177-115">Описывается, как управлять разделителем в элементе управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="35177-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="35177-116">Практическое руководство. Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="35177-116">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="35177-117">Описывается, как управлять ориентацией разделителя в элементе управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="35177-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="35177-118">Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35177-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="35177-119">Описывается создание пользовательского интерфейса с несколькими областями, аналогичного интерфейсу приложения Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="35177-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="35177-120">См. также [как: Разделение окна по горизонтали с помощью конструктора](http://msdn.microsoft.com/library/ms233667\(v=vs.110\)), [как: Создание интерфейса в стиле проводника Windows в Windows Forms](http://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [как: Создание пользовательского интерфейса с несколькими панелями с С помощью конструктора Windows Forms](http://msdn.microsoft.com/library/ms233661\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="35177-120">Also see [How to: Split a Window Horizontally Using the Designer](http://msdn.microsoft.com/library/ms233667\(v=vs.110\)), [How to: Create a Windows Explorer–Style Interface on a Windows Form](http://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](http://msdn.microsoft.com/library/ms233661\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="35177-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="35177-121">Reference</span></span>  
 <span data-ttu-id="35177-122">Класс <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="35177-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="35177-123">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="35177-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="35177-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="35177-124">Related Sections</span></span>  
 [<span data-ttu-id="35177-125">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35177-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="35177-126">Ссылки на разделы, посвященные элементам управления, которые предназначены специально для работы с Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35177-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="35177-127">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35177-127">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="35177-128">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="35177-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
