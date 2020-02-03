---
title: Отображение значков для элемента управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744503"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="13458-102">Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13458-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="13458-103">Элемент управления Windows Forms <xref:System.Windows.Forms.ListView> может отображать значки из трех списков изображений.</span><span class="sxs-lookup"><span data-stu-id="13458-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="13458-104">В представлениях List, Details и маленькие значки отображаются изображения из списка изображений, указанного в свойстве <xref:System.Windows.Forms.ListView.SmallImageList%2A>.</span><span class="sxs-lookup"><span data-stu-id="13458-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="13458-105">В представлении LargeIcon отображаются изображения из списка изображений, указанного в свойстве <xref:System.Windows.Forms.ListView.LargeImageList%2A>.</span><span class="sxs-lookup"><span data-stu-id="13458-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="13458-106">В представлении списка также может отображаться дополнительный набор значков, установленный в свойстве <xref:System.Windows.Forms.ListView.StateImageList%2A> рядом с большим или мелким значками.</span><span class="sxs-lookup"><span data-stu-id="13458-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="13458-107">Дополнительные сведения о списках изображений см. в разделе [ImageList Component](imagelist-component-windows-forms.md) и [инструкции по добавлению или удалению изображений с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="13458-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="13458-108">Отображение изображений в представлении списка</span><span class="sxs-lookup"><span data-stu-id="13458-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="13458-109">Задайте соответствующее свойство (<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>или <xref:System.Windows.Forms.ListView.StateImageList%2A>) для существующего компонента <xref:System.Windows.Forms.ImageList>, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="13458-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="13458-110">Эти свойства можно задать в конструкторе с помощью окно свойств или в коде.</span><span class="sxs-lookup"><span data-stu-id="13458-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="13458-111">Задайте свойство <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> или <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> для каждого элемента списка со связанным значком.</span><span class="sxs-lookup"><span data-stu-id="13458-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="13458-112">Эти свойства можно задать в коде или в **редакторе коллекции ListViewItem**.</span><span class="sxs-lookup"><span data-stu-id="13458-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="13458-113">Чтобы открыть **Редактор коллекции ListViewItem**, нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A> в окне **свойства** .</span><span class="sxs-lookup"><span data-stu-id="13458-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="13458-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13458-114">See also</span></span>

- [<span data-ttu-id="13458-115">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="13458-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="13458-116">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13458-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="13458-117">Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13458-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="13458-118">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="13458-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="13458-119">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="13458-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
