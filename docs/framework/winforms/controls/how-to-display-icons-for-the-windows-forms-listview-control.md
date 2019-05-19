---
title: Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms
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
ms.openlocfilehash: 80a827a88ac92008c7fe2a642d1d4b59a18f89da
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880408"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="7ba98-102">Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ba98-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="7ba98-103">Windows Forms <xref:System.Windows.Forms.ListView> элемент управления может отображать значки из трех списков изображений.</span><span class="sxs-lookup"><span data-stu-id="7ba98-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="7ba98-104">Представления списка, подробности и SmallIcon отображение изображений из списка изображений, указанных в <xref:System.Windows.Forms.ListView.SmallImageList%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7ba98-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="7ba98-105">Представление LargeIcon показывает изображения из списка изображений, указанных в <xref:System.Windows.Forms.ListView.LargeImageList%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7ba98-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="7ba98-106">В представлении списка также может отображаться дополнительный набор значков, заданных в <xref:System.Windows.Forms.ListView.StateImageList%2A> свойство, рядом с крупных или мелких значков.</span><span class="sxs-lookup"><span data-stu-id="7ba98-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="7ba98-107">Дополнительные сведения о списках изображений, см. в разделе [компонента ImageList](imagelist-component-windows-forms.md) и [как: Добавление и удаление изображений с помощью Windows Forms компонента ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="7ba98-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="7ba98-108">Для отображения изображений в виде списка</span><span class="sxs-lookup"><span data-stu-id="7ba98-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="7ba98-109">Задайте соответствующее свойство —<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, или <xref:System.Windows.Forms.ListView.StateImageList%2A>— к существующему <xref:System.Windows.Forms.ImageList> компонента, вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="7ba98-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="7ba98-110">Эти свойства можно задать в конструкторе с помощью окна «Свойства» или в коде.</span><span class="sxs-lookup"><span data-stu-id="7ba98-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="7ba98-111">Задайте <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> или <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> свойство для каждого элемента списка, значок.</span><span class="sxs-lookup"><span data-stu-id="7ba98-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="7ba98-112">Эти свойства можно задать в коде или в **редактор коллекции ListViewItem**.</span><span class="sxs-lookup"><span data-stu-id="7ba98-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="7ba98-113">Чтобы открыть **редактор коллекции ListViewItem**, нажмите кнопку с многоточием (![кнопку с многоточием (...) в окне свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом с полем <xref:System.Windows.Forms.ListView.Items%2A> свойство **Свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="7ba98-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="7ba98-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7ba98-114">See also</span></span>

- [<span data-ttu-id="7ba98-115">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="7ba98-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="7ba98-116">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ba98-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="7ba98-117">Практическое руководство. Добавить столбцы для элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ba98-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="7ba98-118">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7ba98-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="7ba98-119">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="7ba98-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
