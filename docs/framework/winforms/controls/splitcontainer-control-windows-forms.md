---
title: Элемент управления SplitContainer (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: d860763e935c88619e3355661038757d00247dfd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963591"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="db643-102">Элемент управления SplitContainer (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="db643-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="db643-103">Элемент управления Windows Forms `SplitContainer` состоит из двух панелей, разделенных подвижной полосой.</span><span class="sxs-lookup"><span data-stu-id="db643-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="db643-104">При наведении указателя мыши на полосу его форма изменяется, показывая, что полоса является перемещаемой.</span><span class="sxs-lookup"><span data-stu-id="db643-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db643-105">На **панели элементов**этот элемент управления заменяет <xref:System.Windows.Forms.Splitter> элемент управления, который был в предыдущей версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db643-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="db643-106">Элемент управления `SplitContainer` намного предпочтительнее, чем элемент управления <xref:System.Windows.Forms.Splitter>.</span><span class="sxs-lookup"><span data-stu-id="db643-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="db643-107">Класс <xref:System.Windows.Forms.Splitter> по-прежнему имеется в .NET Framework для обеспечения совместимости с существующими приложениями, но для новых проектов настоятельно рекомендуется использовать элемент управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="db643-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="db643-108">С помощью элемента управления `SplitContainer` можно создавать сложные пользовательские интерфейсы. Часто выбор на одной панели определяет объекты, отображаемые на другой.</span><span class="sxs-lookup"><span data-stu-id="db643-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="db643-109">Такой подход является весьма эффективным для отображения и просмотра информации.</span><span class="sxs-lookup"><span data-stu-id="db643-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="db643-110">Две панели позволяют группировать информацию, а полоса или разделитель упрощают изменение размера панелей.</span><span class="sxs-lookup"><span data-stu-id="db643-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db643-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="db643-111">In This Section</span></span>  
 [<span data-ttu-id="db643-112">Общие сведения о компоненте SplitContainer</span><span class="sxs-lookup"><span data-stu-id="db643-112">SplitContainer Control Overview</span></span>](splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="db643-113">Приводятся основные сведения об элементе управления `SplitContainer`, и описываются его часто используемые свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="db643-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="db643-114">Практическое руководство. Определение поведения изменения размера и позиционирования в окне с разделением</span><span class="sxs-lookup"><span data-stu-id="db643-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="db643-115">Описывается, как управлять разделителем в элементе управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="db643-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="db643-116">Практическое руководство. Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="db643-116">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="db643-117">Описывается, как управлять ориентацией разделителя в элементе управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="db643-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="db643-118">Практическое руководство. Создание пользовательского интерфейса с несколькими панелями с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db643-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="db643-119">Описывается создание пользовательского интерфейса с несколькими областями, аналогичного интерфейсу приложения Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="db643-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="db643-120">Также см. раздел [Как Разделение окна по горизонтали с помощью](how-to-split-a-window-horizontally-using-the-designer.md)конструктора [, как: Создание интерфейса в стиле проводника Windows в Windows Forms](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [как: Создание пользовательского интерфейса с несколькими панелями с Windows Forms с помощью](create-a-multipane-user-interface-with-wf-using-the-designer.md)конструктора.</span><span class="sxs-lookup"><span data-stu-id="db643-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="db643-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="db643-121">Reference</span></span>  
 <span data-ttu-id="db643-122">Класс <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="db643-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="db643-123">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="db643-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="db643-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="db643-124">Related Sections</span></span>  
 [<span data-ttu-id="db643-125">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db643-125">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="db643-126">Ссылки на разделы, посвященные элементам управления, которые предназначены специально для работы с Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="db643-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="db643-127">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db643-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="db643-128">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="db643-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
