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
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458848"
---
# <a name="how-to-create-a-binding-in-code"></a>Практическое руководство. Создание привязки в коде
В этом примере показано, как создать и задать <xref:System.Windows.Data.Binding> в коде.  
  
## <a name="example"></a>Пример  
 Класс <xref:System.Windows.FrameworkElement> и класс <xref:System.Windows.FrameworkContentElement> предоставляют метод `SetBinding`. При привязке элемента, который наследует любой из этих классов, можно вызвать метод <xref:System.Windows.FrameworkElement.SetBinding%2A> напрямую.  
  
 В следующем примере создается класс с именем, `MyData`, который содержит свойство с именем `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 В следующем примере показано, как создать объект привязки для задания источника привязки.  В примере используется <xref:System.Windows.FrameworkElement.SetBinding%2A> для привязки свойства <xref:System.Windows.Controls.TextBlock.Text%2A> `myText`, которое является <xref:System.Windows.Controls.TextBlock>ным элементом управления, для `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Полный пример кода см. в разделе [Пример привязки только для кода](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Вместо вызова <xref:System.Windows.FrameworkElement.SetBinding%2A>можно использовать статический метод <xref:System.Windows.Data.BindingOperations.SetBinding%2A> класса <xref:System.Windows.Data.BindingOperations>. В следующем примере вызывается <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> вместо <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> для привязки `myText` к `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
