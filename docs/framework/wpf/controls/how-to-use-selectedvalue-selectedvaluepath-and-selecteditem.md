---
title: Практическое руководство. Использование элементов SelectedValue, SelectedValuePath и SelectedItem
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: d9f7a8f04f53b7d38a49dfef2c947dfa1c2d263d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169711"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="b2d5e-102">Практическое руководство. Использование элементов SelectedValue, SelectedValuePath и SelectedItem</span><span class="sxs-lookup"><span data-stu-id="b2d5e-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="b2d5e-103">В этом примере показано, как использовать <xref:System.Windows.Controls.TreeView.SelectedValue%2A> и <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> свойства, чтобы указать значение для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> из <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2d5e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b2d5e-104">Example</span></span>  
 <span data-ttu-id="b2d5e-105"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Свойство позволяет указать <xref:System.Windows.Controls.TreeView.SelectedValue%2A> для <xref:System.Windows.Controls.TreeView.SelectedItem%2A> в <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="b2d5e-106"><xref:System.Windows.Controls.TreeView.SelectedItem%2A> Представляет объект в <xref:System.Windows.Controls.ItemsControl.Items%2A> коллекции и <xref:System.Windows.Controls.TreeView> отображает значение одного свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="b2d5e-107"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Задает путь к свойству, которое используется для определения значения <xref:System.Windows.Controls.TreeView.SelectedValue%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="b2d5e-108">В примерах этого раздела показана эта концепция.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="b2d5e-109">В следующем примере показан <xref:System.Windows.Data.XmlDataProvider> , содержащий сведения о сотрудниках.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="b2d5e-110">В следующем примере определяется <xref:System.Windows.HierarchicalDataTemplate> , отображающий `EmployeeName` и `EmployeeWorkDay` из `Employee`.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="b2d5e-111">Обратите внимание, что <xref:System.Windows.HierarchicalDataTemplate> не указывает `EmployeeNumber` как часть шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="b2d5e-112">В следующем примере показан <xref:System.Windows.Controls.TreeView> , использующий ранее определенный <xref:System.Windows.HierarchicalDataTemplate> и устанавливает <xref:System.Windows.Controls.TreeView.SelectedValue%2A> свойства `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="b2d5e-113">При выборе `EmployeeName` в <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> возвращает `EmployeeInfo` элемент данных, соответствующий выбранной `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="b2d5e-114">Тем не менее так как <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> этого <xref:System.Windows.Controls.TreeView> присваивается `EmployeeNumber`, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> присваивается `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="b2d5e-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="b2d5e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b2d5e-115">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="b2d5e-116">Обзор элемента управления "TreeView"</span><span class="sxs-lookup"><span data-stu-id="b2d5e-116">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="b2d5e-117">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="b2d5e-117">How-to Topics</span></span>](treeview-how-to-topics.md)
