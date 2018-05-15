---
title: Практическое руководство. Добавление в элемент управления ListView возможностей поиска
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: 2049638998f7a8d099e14fab9c95384a49c67833
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="c6216-102">Практическое руководство. Добавление в элемент управления ListView возможностей поиска</span><span class="sxs-lookup"><span data-stu-id="c6216-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="c6216-103">Зачастую при работе с большой список элементов в <xref:System.Windows.Forms.ListView> элемента управления, необходимо предоставить пользователям возможности поиска.</span><span class="sxs-lookup"><span data-stu-id="c6216-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="c6216-104"><xref:System.Windows.Forms.ListView> Управления обеспечивает такую функцию двумя способами: поиск совпадений текста и поиск расположений.</span><span class="sxs-lookup"><span data-stu-id="c6216-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="c6216-105"><xref:System.Windows.Forms.ListView.FindItemWithText%2A> Метод позволяет выполнять поиск текста в <xref:System.Windows.Forms.ListView> в представлении списка или подробных сведений, заданным строку поиска и необязательного начального и конечного индекса.</span><span class="sxs-lookup"><span data-stu-id="c6216-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="c6216-106">Напротив <xref:System.Windows.Forms.ListView.FindNearestItem%2A> метод позволяет находить элементы в <xref:System.Windows.Forms.ListView> в представлении значков или эскизов, исходя из набора координат x и y и направление поиска.</span><span class="sxs-lookup"><span data-stu-id="c6216-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="c6216-107">Чтобы найти элемент с помощью текста</span><span class="sxs-lookup"><span data-stu-id="c6216-107">To find an item using text</span></span>  
  
1.  <span data-ttu-id="c6216-108">Создание <xref:System.Windows.Forms.ListView> с <xref:System.Windows.Forms.ListView.View%2A> свойству присвоено <xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.List>, а затем заполнить <xref:System.Windows.Forms.ListView> с элементами.</span><span class="sxs-lookup"><span data-stu-id="c6216-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="c6216-109">Вызовите <xref:System.Windows.Forms.ListView.FindItemWithText%2A> метод, передав текст элемента, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="c6216-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3.  <span data-ttu-id="c6216-110">В следующем примере кода показано, как создать простую <xref:System.Windows.Forms.ListView>, заполнить его элементами и использовать введенный пользователем текст для поиска элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="c6216-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="c6216-111">Чтобы найти элемент с помощью координат x и y</span><span class="sxs-lookup"><span data-stu-id="c6216-111">To find an item using x- and y-coordinates</span></span>  
  
1.  <span data-ttu-id="c6216-112">Создание <xref:System.Windows.Forms.ListView> с <xref:System.Windows.Forms.View> свойству присвоено <xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>, а затем заполнить <xref:System.Windows.Forms.ListView> с элементами.</span><span class="sxs-lookup"><span data-stu-id="c6216-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="c6216-113">Вызовите <xref:System.Windows.Forms.ListView.FindNearestItem%2A> метод, передав нужные координаты x и y — и направление поиска.</span><span class="sxs-lookup"><span data-stu-id="c6216-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3.  <span data-ttu-id="c6216-114">В следующем примере кода демонстрируется способ создания основных значок <xref:System.Windows.Forms.ListView>, заполнение ее элементов и отслеживания <xref:System.Windows.Forms.Control.MouseDown> событий для поиска ближайшего элемента по оси вверх.</span><span class="sxs-lookup"><span data-stu-id="c6216-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c6216-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c6216-115">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [<span data-ttu-id="c6216-116">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="c6216-116">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="c6216-117">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="c6216-117">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="c6216-118">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c6216-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
