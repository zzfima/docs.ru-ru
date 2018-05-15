---
title: Практическое руководство. Создание привязки в коде
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 62c5610bf5590594f34a3401b9397bb17d23f5ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="32cff-102">Практическое руководство. Создание привязки в коде</span><span class="sxs-lookup"><span data-stu-id="32cff-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="32cff-103">В этом примере показано, как создать и установить <xref:System.Windows.Data.Binding> в коде.</span><span class="sxs-lookup"><span data-stu-id="32cff-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32cff-104">Пример</span><span class="sxs-lookup"><span data-stu-id="32cff-104">Example</span></span>  
 <span data-ttu-id="32cff-105"><xref:System.Windows.FrameworkElement> Класса и <xref:System.Windows.FrameworkContentElement> предоставляют `SetBinding` метод.</span><span class="sxs-lookup"><span data-stu-id="32cff-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="32cff-106">При привязке элемента, наследующего от любого из этих классов можно вызвать <xref:System.Windows.FrameworkElement.SetBinding%2A> метод непосредственно.</span><span class="sxs-lookup"><span data-stu-id="32cff-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="32cff-107">В следующем примере создается класс с именем, `MyData`, который содержит свойство с именем `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="32cff-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="32cff-108">В следующем примере показано создание объекта привязки для задания источника привязки.</span><span class="sxs-lookup"><span data-stu-id="32cff-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="32cff-109">В этом примере <xref:System.Windows.FrameworkElement.SetBinding%2A> для привязки <xref:System.Windows.Controls.TextBlock.Text%2A> свойство `myText`, который является <xref:System.Windows.Controls.TextBlock> элемента управления, `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="32cff-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="32cff-110">Полный пример кода, в разделе [код только образец привязки](http://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span><span class="sxs-lookup"><span data-stu-id="32cff-110">For the complete code sample, see [Code-only Binding Sample](http://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="32cff-111">Вместо вызова метода <xref:System.Windows.FrameworkElement.SetBinding%2A>, можно использовать <xref:System.Windows.Data.BindingOperations.SetBinding%2A> статический метод <xref:System.Windows.Data.BindingOperations> класса.</span><span class="sxs-lookup"><span data-stu-id="32cff-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="32cff-112">Следующий пример, вызовы <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> вместо <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> для привязки `myText` для `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="32cff-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="32cff-113">См. также</span><span class="sxs-lookup"><span data-stu-id="32cff-113">See Also</span></span>  
 [<span data-ttu-id="32cff-114">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="32cff-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="32cff-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="32cff-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
