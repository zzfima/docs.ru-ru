---
title: Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 19d0b284238ed662b25627d6077c1ebe6ecc6e86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323711"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="e59c9-102">Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e59c9-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="e59c9-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="e59c9-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <xref:System.Windows.Forms.ToolBar> <span data-ttu-id="e59c9-104">кнопки, могут отображать значки для упрощения идентификации пользователей.</span><span class="sxs-lookup"><span data-stu-id="e59c9-104">buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="e59c9-105">Это достигается с помощью добавления изображений к <xref:System.Windows.Forms.ImageList> компонента и его сопоставления с <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e59c9-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
 <span data-ttu-id="e59c9-106">Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ToolBar> управления и <xref:System.Windows.Forms.ImageList> компонента.</span><span class="sxs-lookup"><span data-stu-id="e59c9-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="e59c9-107">Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e59c9-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e59c9-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="e59c9-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e59c9-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="e59c9-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e59c9-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e59c9-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="e59c9-111">Чтобы задать значок для кнопки панели инструментов во время разработки</span><span class="sxs-lookup"><span data-stu-id="e59c9-111">To set an icon for a toolbar button at design time</span></span>  
  
1. <span data-ttu-id="e59c9-112">Добавление изображений к <xref:System.Windows.Forms.ImageList> компонента.</span><span class="sxs-lookup"><span data-stu-id="e59c9-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="e59c9-113">Дополнительные сведения см. в разделе [Как Добавление или удаление изображений из компонента ImageList с помощью конструктора](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e59c9-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>  
  
2. <span data-ttu-id="e59c9-114">Выберите <xref:System.Windows.Forms.ToolBar> элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="e59c9-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>  
  
3. <span data-ttu-id="e59c9-115">В **свойства** окне <xref:System.Windows.Forms.ToolBar> элемента управления <xref:System.Windows.Forms.ToolBar.ImageList%2A> свойства <xref:System.Windows.Forms.ImageList> компонента.</span><span class="sxs-lookup"><span data-stu-id="e59c9-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
4. <span data-ttu-id="e59c9-116">Нажмите кнопку <xref:System.Windows.Forms.ToolBar> элемента управления <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство, чтобы выбрать его и нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **Редактора коллекции**.</span><span class="sxs-lookup"><span data-stu-id="e59c9-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
5. <span data-ttu-id="e59c9-117">Используйте **добавить** , чтобы добавить кнопки для <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e59c9-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
6. <span data-ttu-id="e59c9-118">В **свойства** окно, которое появляется на правой стороне панели **редактора коллекции**, задайте <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> свойства каждой кнопки панели инструментов, одно из значений в списке, который извлекается из образов, добавленных к <xref:System.Windows.Forms.ImageList> компонента.</span><span class="sxs-lookup"><span data-stu-id="e59c9-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e59c9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e59c9-119">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="e59c9-120">Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar</span><span class="sxs-lookup"><span data-stu-id="e59c9-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="e59c9-121">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="e59c9-121">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="e59c9-122">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="e59c9-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
