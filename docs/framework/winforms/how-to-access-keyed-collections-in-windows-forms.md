---
title: Практическое руководство. Доступ к коллекциям с ключом в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: fdd3a56ab9a267990bb0e832c0d4cc2af9334034
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801833"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="6e42c-102">Практическое руководство. Доступ к коллекциям с ключом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e42c-102">How to: Access Keyed Collections in Windows Forms</span></span>
- <span data-ttu-id="6e42c-103">Можно получить доступ к ее отдельные элементы по ключу.</span><span class="sxs-lookup"><span data-stu-id="6e42c-103">You can access individual collection items by key.</span></span> <span data-ttu-id="6e42c-104">Эта функциональность была добавлена для многих классов коллекций, которые обычно используются приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6e42c-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="6e42c-105">Ниже перечислены некоторые из классов коллекций, имеющих доступны коллекции с ключом.</span><span class="sxs-lookup"><span data-stu-id="6e42c-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="6e42c-106">Ключ, связанный с элементом в коллекции, обычно является имя элемента.</span><span class="sxs-lookup"><span data-stu-id="6e42c-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="6e42c-107">Следующие процедуры показывают, как использовать классы коллекций для выполнения распространенных задач.</span><span class="sxs-lookup"><span data-stu-id="6e42c-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="6e42c-108">Чтобы найти и передать фокус для вложенного элемента управления в коллекции элементов управления</span><span class="sxs-lookup"><span data-stu-id="6e42c-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="6e42c-109">Используйте <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> и <xref:System.Windows.Forms.Control.Focus%2A> методы, чтобы указать имя элемента управления, чтобы найти и передать фокус.</span><span class="sxs-lookup"><span data-stu-id="6e42c-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="6e42c-110">Для доступа к изображению в коллекции изображений</span><span class="sxs-lookup"><span data-stu-id="6e42c-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="6e42c-111">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> свойство, чтобы указать имя образа, необходимо получить доступ.</span><span class="sxs-lookup"><span data-stu-id="6e42c-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="6e42c-112">Чтобы задать страницу вкладки в качестве выбранной вкладки</span><span class="sxs-lookup"><span data-stu-id="6e42c-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="6e42c-113">Используйте <xref:System.Windows.Forms.TabControl.SelectedTab%2A> свойство вместе с <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> свойство, чтобы указать имя страницы вкладки, чтобы задать в качестве выбранной вкладки.</span><span class="sxs-lookup"><span data-stu-id="6e42c-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6e42c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6e42c-114">See also</span></span>

- [<span data-ttu-id="6e42c-115">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e42c-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="6e42c-116">Практическое руководство. Добавление или удаление изображений с помощью компонента ImageList в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e42c-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
