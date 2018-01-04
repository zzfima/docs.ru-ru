---
title: "Практическое руководство. Доступ к коллекциям с ключом в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 852e82aff12dc39adeba6ea2dada5934ae55f951
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="29494-102">Практическое руководство. Доступ к коллекциям с ключом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29494-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="29494-103">Отдельные элементы коллекции доступны по ключу.</span><span class="sxs-lookup"><span data-stu-id="29494-103">You can access individual collection items by key.</span></span> <span data-ttu-id="29494-104">Эта функция будет добавлен во многих классах коллекций, которые обычно используются приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="29494-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="29494-105">Ниже перечислены некоторые из классов коллекций, которые имеют доступ коллекции с ключом.</span><span class="sxs-lookup"><span data-stu-id="29494-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="29494-106">Ключ, связанный с элементом в коллекции, обычно является имя элемента.</span><span class="sxs-lookup"><span data-stu-id="29494-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="29494-107">Следующие процедуры показывают, как использовать классы коллекций для выполнения стандартных задач.</span><span class="sxs-lookup"><span data-stu-id="29494-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="29494-108">Чтобы найти и передать фокус вложенному элементу управления в коллекции элементов управления</span><span class="sxs-lookup"><span data-stu-id="29494-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="29494-109">Используйте <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> и <xref:System.Windows.Forms.Control.Focus%2A> методов, чтобы указать имя элемента управления, чтобы найти и передать фокус.</span><span class="sxs-lookup"><span data-stu-id="29494-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="29494-110">Для доступа к изображению в коллекции изображений</span><span class="sxs-lookup"><span data-stu-id="29494-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="29494-111">Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> свойство, чтобы указать имя образа, которым требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="29494-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="29494-112">Чтобы задать страницу вкладки в качестве выбранной вкладки</span><span class="sxs-lookup"><span data-stu-id="29494-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="29494-113">Используйте <xref:System.Windows.Forms.TabControl.SelectedTab%2A> свойство вместе с <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> свойство, чтобы указать имя вкладки, которую следует задать в качестве выбранной вкладки.</span><span class="sxs-lookup"><span data-stu-id="29494-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="29494-114">См. также</span><span class="sxs-lookup"><span data-stu-id="29494-114">See Also</span></span>  
 [<span data-ttu-id="29494-115">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29494-115">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="29494-116">Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29494-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
