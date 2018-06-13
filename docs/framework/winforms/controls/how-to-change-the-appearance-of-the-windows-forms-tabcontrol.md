---
title: Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 1ea2208229d790f69e517d55e2de5ee042bdfb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531044"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="bf198-102">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bf198-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="bf198-103">Можно изменить внешний вид вкладок в формах Windows Forms с помощью свойства <xref:System.Windows.Forms.TabControl> и <xref:System.Windows.Forms.TabPage> объекты, составляющие отдельные вкладки в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="bf198-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="bf198-104">Настройка этих свойств, можно отображать рисунки на вкладках, отображение вкладок вертикально, отображения нескольких рядов и также включить или отключить вкладки программными средствами.</span><span class="sxs-lookup"><span data-stu-id="bf198-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="bf198-105">Для отображения значка Метка части вкладки</span><span class="sxs-lookup"><span data-stu-id="bf198-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="bf198-106">Добавить <xref:System.Windows.Forms.ImageList> на форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bf198-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="bf198-107">Добавление изображений в списке изображений.</span><span class="sxs-lookup"><span data-stu-id="bf198-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="bf198-108">Дополнительные сведения о списках изображений см. в разделе [компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [как: Добавление и удаление изображений с помощью компонента ImageList в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="bf198-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="bf198-109">Задать <xref:System.Windows.Forms.TabControl.ImageList%2A> свойство <xref:System.Windows.Forms.TabControl> для <xref:System.Windows.Forms.ImageList> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bf198-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="bf198-110">Задать <xref:System.Windows.Forms.TabPage.ImageIndex%2A> свойство <xref:System.Windows.Forms.TabPage> индекс соответствующего рисунка в списке.</span><span class="sxs-lookup"><span data-stu-id="bf198-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="bf198-111">Чтобы создать несколько рядов вкладок</span><span class="sxs-lookup"><span data-stu-id="bf198-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="bf198-112">Добавление номера страниц вкладок, которые нужно.</span><span class="sxs-lookup"><span data-stu-id="bf198-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="bf198-113">Задать <xref:System.Windows.Forms.TabControl.Multiline%2A> свойство <xref:System.Windows.Forms.TabControl> для `true`.</span><span class="sxs-lookup"><span data-stu-id="bf198-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="bf198-114">Если вкладки не отображается в несколько строк, задайте <xref:System.Windows.Forms.Control.Width%2A> свойство <xref:System.Windows.Forms.TabControl> быть уже, чем все вкладки.</span><span class="sxs-lookup"><span data-stu-id="bf198-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="bf198-115">Расположение вкладок вдоль края элемента управления</span><span class="sxs-lookup"><span data-stu-id="bf198-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="bf198-116">Задать <xref:System.Windows.Forms.TabControl.Alignment%2A> свойство <xref:System.Windows.Forms.TabControl> для <xref:System.Windows.Forms.TabAlignment.Left> или <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="bf198-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="bf198-117">Чтобы включить или отключить все элементы управления на вкладке</span><span class="sxs-lookup"><span data-stu-id="bf198-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="bf198-118">Задать <xref:System.Windows.Forms.TabPage.Enabled%2A> свойство <xref:System.Windows.Forms.TabPage> для `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="bf198-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="bf198-119">Отображение вкладок как кнопки</span><span class="sxs-lookup"><span data-stu-id="bf198-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="bf198-120">Задать <xref:System.Windows.Forms.TabControl.Appearance%2A> свойство <xref:System.Windows.Forms.TabControl> для <xref:System.Windows.Forms.TabAppearance.Buttons> или <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="bf198-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf198-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bf198-121">See Also</span></span>  
 [<span data-ttu-id="bf198-122">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="bf198-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="bf198-123">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="bf198-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="bf198-124">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="bf198-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="bf198-125">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="bf198-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="bf198-126">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bf198-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
