---
title: Изменение внешнего вида элемента TabControl
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
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746608"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="385b3-102">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="385b3-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="385b3-103">Внешний вид вкладок в Windows Forms можно изменить с помощью свойств <xref:System.Windows.Forms.TabControl> и объектов <xref:System.Windows.Forms.TabPage>, которые составляют отдельные вкладки в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="385b3-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="385b3-104">Устанавливая эти свойства, можно отображать изображения на вкладках, отображать вкладки вертикально, а не горизонтально, отображать несколько строк вкладок, а также включать и отключать вкладки программным способом.</span><span class="sxs-lookup"><span data-stu-id="385b3-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="385b3-105">Отображение значка в части метки вкладки</span><span class="sxs-lookup"><span data-stu-id="385b3-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="385b3-106">Добавьте в форму элемент управления <xref:System.Windows.Forms.ImageList>.</span><span class="sxs-lookup"><span data-stu-id="385b3-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="385b3-107">Добавление изображений в список изображений.</span><span class="sxs-lookup"><span data-stu-id="385b3-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="385b3-108">Дополнительные сведения о списках изображений см. в разделе [ImageList Component](imagelist-component-windows-forms.md) и [инструкции по добавлению или удалению изображений с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="385b3-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="385b3-109">Задайте для свойства <xref:System.Windows.Forms.TabControl.ImageList%2A> <xref:System.Windows.Forms.TabControl> элемент управления <xref:System.Windows.Forms.ImageList>.</span><span class="sxs-lookup"><span data-stu-id="385b3-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="385b3-110">Задайте для свойства <xref:System.Windows.Forms.TabPage.ImageIndex%2A> <xref:System.Windows.Forms.TabPage> индекс соответствующего изображения в списке.</span><span class="sxs-lookup"><span data-stu-id="385b3-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="385b3-111">Создание нескольких строк вкладок</span><span class="sxs-lookup"><span data-stu-id="385b3-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="385b3-112">Добавьте нужное число страниц вкладок.</span><span class="sxs-lookup"><span data-stu-id="385b3-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="385b3-113">Задайте для свойства <xref:System.Windows.Forms.TabControl.Multiline%2A> <xref:System.Windows.Forms.TabControl> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="385b3-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="385b3-114">Если вкладки еще не отображаются в нескольких строках, установите свойство <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.TabControl>, чтобы оно было более узким, чем все вкладки.</span><span class="sxs-lookup"><span data-stu-id="385b3-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="385b3-115">Размещение вкладок на стороне элемента управления</span><span class="sxs-lookup"><span data-stu-id="385b3-115">To arrange tabs on the side of the control</span></span>  
  
- <span data-ttu-id="385b3-116">Задайте для свойства <xref:System.Windows.Forms.TabControl.Alignment%2A> <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.TabAlignment.Left> или <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="385b3-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="385b3-117">Программное включение или отключение всех элементов управления на вкладке</span><span class="sxs-lookup"><span data-stu-id="385b3-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="385b3-118">Задайте для свойства <xref:System.Windows.Forms.TabPage.Enabled%2A> <xref:System.Windows.Forms.TabPage> значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="385b3-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="385b3-119">Отображение вкладок в виде кнопок</span><span class="sxs-lookup"><span data-stu-id="385b3-119">To display tabs as buttons</span></span>  
  
- <span data-ttu-id="385b3-120">Задайте для свойства <xref:System.Windows.Forms.TabControl.Appearance%2A> <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.TabAppearance.Buttons> или <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="385b3-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385b3-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="385b3-121">See also</span></span>

- [<span data-ttu-id="385b3-122">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="385b3-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="385b3-123">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="385b3-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="385b3-124">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="385b3-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="385b3-125">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="385b3-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="385b3-126">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="385b3-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
