---
title: Руководство. доступ к коллекциям с ключом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739614"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="c1528-102">Практическое руководство. Доступ к коллекциям с ключом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1528-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="c1528-103">К отдельным элементам коллекции можно обращаться по ключу.</span><span class="sxs-lookup"><span data-stu-id="c1528-103">You can access individual collection items by key.</span></span> <span data-ttu-id="c1528-104">Эта функция добавлена во многие классы коллекций, которые обычно используются приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c1528-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="c1528-105">В следующем списке показаны некоторые классы коллекций, имеющие доступные коллекции с ключом:</span><span class="sxs-lookup"><span data-stu-id="c1528-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="c1528-106">Ключом, связанным с элементом в коллекции, обычно является имя элемента.</span><span class="sxs-lookup"><span data-stu-id="c1528-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="c1528-107">В следующих процедурах показано, как использовать классы коллекций для выполнения стандартных задач.</span><span class="sxs-lookup"><span data-stu-id="c1528-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="c1528-108">Поиск и передача фокуса вложенному элементу управления в коллекции элементов управления</span><span class="sxs-lookup"><span data-stu-id="c1528-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="c1528-109">Используйте методы <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> и <xref:System.Windows.Forms.Control.Focus%2A>, чтобы указать имя элемента управления, который нужно найти, и присвоить ему фокус.</span><span class="sxs-lookup"><span data-stu-id="c1528-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="c1528-110">Получение доступа к изображению в коллекции изображений</span><span class="sxs-lookup"><span data-stu-id="c1528-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="c1528-111">Используйте свойство <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A>, чтобы указать имя образа, к которому требуется получить доступ.</span><span class="sxs-lookup"><span data-stu-id="c1528-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="c1528-112">Задание страницы вкладки в качестве выбранной вкладки</span><span class="sxs-lookup"><span data-stu-id="c1528-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="c1528-113">Используйте свойство <xref:System.Windows.Forms.TabControl.SelectedTab%2A> вместе со свойством <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A>, чтобы указать имя страницы вкладки, которая будет задана в качестве выбранной вкладки.</span><span class="sxs-lookup"><span data-stu-id="c1528-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c1528-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1528-114">See also</span></span>

- [<span data-ttu-id="c1528-115">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1528-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="c1528-116">Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1528-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
