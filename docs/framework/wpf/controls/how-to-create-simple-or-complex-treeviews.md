---
title: Практическое руководство. Создание простых или сложных элементов TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205151"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="2c26d-102">Практическое руководство. Создание простых или сложных элементов TreeView</span><span class="sxs-lookup"><span data-stu-id="2c26d-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="2c26d-103">В этом примере показано, как создавать простые и комплексные <xref:System.Windows.Controls.TreeView> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="2c26d-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="2c26d-104">Объект <xref:System.Windows.Controls.TreeView> состоит из иерархии <xref:System.Windows.Controls.TreeViewItem> элементов управления, которые могут содержать простые текстовые строки, а также более сложное содержимое, такие как <xref:System.Windows.Controls.Button> элементов управления или <xref:System.Windows.Controls.StackPanel> с внедренным содержимым.</span><span class="sxs-lookup"><span data-stu-id="2c26d-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="2c26d-105">Можно явно определить <xref:System.Windows.Controls.TreeView> содержимое или источник данных может предоставить содержимое.</span><span class="sxs-lookup"><span data-stu-id="2c26d-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="2c26d-106">В этом разделе приведены примеры этих понятий.</span><span class="sxs-lookup"><span data-stu-id="2c26d-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c26d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2c26d-107">Example</span></span>  
 <span data-ttu-id="2c26d-108"><xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Свойство <xref:System.Windows.Controls.TreeViewItem> с содержимым, <xref:System.Windows.Controls.TreeView> отображает для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="2c26d-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="2c26d-109">Объект <xref:System.Windows.Controls.TreeViewItem> может также иметь <xref:System.Windows.Controls.TreeViewItem> элементов управления, а его дочерние элементы можно определить эти дочерние элементы с помощью <xref:System.Windows.Controls.ItemsControl.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="2c26d-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="2c26d-110">В следующем примере показано, как явно определить <xref:System.Windows.Controls.TreeViewItem> содержимого, задав <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> свойство в текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="2c26d-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="2c26d-111">В следующем примере показано, как определить дочерние элементы <xref:System.Windows.Controls.TreeViewItem> , определив <xref:System.Windows.Controls.ItemsControl.Items%2A> , которые <xref:System.Windows.Controls.Button> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="2c26d-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="2c26d-112">В следующем примере показано, как создать <xref:System.Windows.Controls.TreeView> где <xref:System.Windows.Data.XmlDataProvider> предоставляет <xref:System.Windows.Controls.TreeViewItem> содержимого и <xref:System.Windows.HierarchicalDataTemplate> определяет внешний вид содержимого.</span><span class="sxs-lookup"><span data-stu-id="2c26d-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="2c26d-113">В следующем примере показано, как создать <xref:System.Windows.Controls.TreeView> где <xref:System.Windows.Controls.TreeViewItem> содержимое содержит <xref:System.Windows.Controls.DockPanel> элементов управления, которые содержат вложенное содержимое.</span><span class="sxs-lookup"><span data-stu-id="2c26d-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="2c26d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2c26d-114">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="2c26d-115">Обзор элемента управления "TreeView"</span><span class="sxs-lookup"><span data-stu-id="2c26d-115">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="2c26d-116">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="2c26d-116">How-to Topics</span></span>](treeview-how-to-topics.md)
