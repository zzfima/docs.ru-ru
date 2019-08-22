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
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666206"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="8929d-102">Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="8929d-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="8929d-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="8929d-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="8929d-104"><xref:System.Windows.Forms.ToolBar>кнопки могут отображать значки в них для простоты идентификации пользователями.</span><span class="sxs-lookup"><span data-stu-id="8929d-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="8929d-105">Это достигается путем добавления изображений в <xref:System.Windows.Forms.ImageList> компонент и их связывания <xref:System.Windows.Forms.ToolBar> с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="8929d-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="8929d-106">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ToolBar> элемент управления и <xref:System.Windows.Forms.ImageList> компонент.</span><span class="sxs-lookup"><span data-stu-id="8929d-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="8929d-107">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8929d-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="8929d-108">Задание значка для кнопки панели инструментов во время разработки</span><span class="sxs-lookup"><span data-stu-id="8929d-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="8929d-109">Добавление изображений в <xref:System.Windows.Forms.ImageList> компонент.</span><span class="sxs-lookup"><span data-stu-id="8929d-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="8929d-110">Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление изображений ImageList с помощью конструктора](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8929d-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="8929d-111"><xref:System.Windows.Forms.ToolBar> Выберите элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="8929d-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="8929d-112">В окне **Свойства** задайте <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ImageList> компоненту <xref:System.Windows.Forms.ToolBar.ImageList%2A> свойство элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8929d-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="8929d-113">![](./media/visual-studio-ellipsis-button.png)Щелкните свойство элементауправления,чтобывыбратьего,инажмитекнопкусмноготочием(...)вокносвойствкнопкиVisualStudio.),чтобыоткрытьредакторколлекцииToolBarButton.<xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.Buttons%2A></span><span class="sxs-lookup"><span data-stu-id="8929d-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="8929d-114">Используйте кнопку **Добавить** , чтобы добавить кнопки в <xref:System.Windows.Forms.ToolBar> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="8929d-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="8929d-115">В окне **Свойства** , которое отображается в правой части окна **Редактор коллекции ToolBarButton** <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> , задайте для свойства каждой кнопки панели инструментов одно из значений в списке, которое отображается из изображений, добавленных в <xref:System.Windows.Forms.ImageList> компонент.</span><span class="sxs-lookup"><span data-stu-id="8929d-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="8929d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8929d-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="8929d-117">Практическое руководство. События меню триггера для кнопок панели инструментов</span><span class="sxs-lookup"><span data-stu-id="8929d-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="8929d-118">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="8929d-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="8929d-119">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="8929d-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
