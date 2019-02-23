---
title: Элемент управления SplitContainer (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: 0afc1aba32852406b975cc65ab4d4bff334d3ff7
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745467"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="0e318-102">Элемент управления SplitContainer (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0e318-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="0e318-103">Элемент управления Windows Forms `SplitContainer` состоит из двух панелей, разделенных подвижной полосой.</span><span class="sxs-lookup"><span data-stu-id="0e318-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="0e318-104">При наведении указателя мыши на полосу его форма изменяется, показывая, что полоса является перемещаемой.</span><span class="sxs-lookup"><span data-stu-id="0e318-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e318-105">В **элементов**, этот элемент управления заменяет <xref:System.Windows.Forms.Splitter> элемента управления, который имелся в предыдущей версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0e318-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="0e318-106">Элемент управления `SplitContainer` намного предпочтительнее, чем элемент управления <xref:System.Windows.Forms.Splitter>.</span><span class="sxs-lookup"><span data-stu-id="0e318-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="0e318-107">Класс <xref:System.Windows.Forms.Splitter> по-прежнему имеется в .NET Framework для обеспечения совместимости с существующими приложениями, но для новых проектов настоятельно рекомендуется использовать элемент управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="0e318-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="0e318-108">С помощью элемента управления `SplitContainer` можно создавать сложные пользовательские интерфейсы. Часто выбор на одной панели определяет объекты, отображаемые на другой.</span><span class="sxs-lookup"><span data-stu-id="0e318-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="0e318-109">Такой подход является весьма эффективным для отображения и просмотра информации.</span><span class="sxs-lookup"><span data-stu-id="0e318-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="0e318-110">Две панели позволяют группировать информацию, а полоса или разделитель упрощают изменение размера панелей.</span><span class="sxs-lookup"><span data-stu-id="0e318-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e318-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0e318-111">In This Section</span></span>  
 [<span data-ttu-id="0e318-112">Общие сведения о компоненте SplitContainer</span><span class="sxs-lookup"><span data-stu-id="0e318-112">SplitContainer Control Overview</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="0e318-113">Приводятся основные сведения об элементе управления `SplitContainer`, и описываются его часто используемые свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="0e318-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="0e318-114">Практическое руководство. Определение изменения размеров и позиционирования в окне с перемещаемым разделителем</span><span class="sxs-lookup"><span data-stu-id="0e318-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="0e318-115">Описывается, как управлять разделителем в элементе управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="0e318-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="0e318-116">Практическое руководство. Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="0e318-116">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="0e318-117">Описывается, как управлять ориентацией разделителя в элементе управления `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="0e318-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="0e318-118">Практическое руководство. Создание с несколькими областями пользовательского интерфейса с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e318-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="0e318-119">Описывается создание пользовательского интерфейса с несколькими областями, аналогичного интерфейсу приложения Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="0e318-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="0e318-120">Также см. раздел [Как Разделение окна по горизонтали с помощью конструктора](how-to-split-a-window-horizontally-using-the-designer.md), [как: Создание интерфейса в стиле проводника Windows в форме Windows](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [как: Создание с несколькими областями пользовательского интерфейса с помощью Windows Forms с помощью конструктора](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="0e318-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0e318-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0e318-121">Reference</span></span>  
 <span data-ttu-id="0e318-122">Класс <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="0e318-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="0e318-123">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="0e318-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0e318-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0e318-124">Related Sections</span></span>  
 [<span data-ttu-id="0e318-125">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e318-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="0e318-126">Ссылки на разделы, посвященные элементам управления, которые предназначены специально для работы с Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0e318-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="0e318-127">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e318-127">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="0e318-128">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="0e318-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
