---
title: Практическое руководство. Оформление дочерних объектов панели
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Практическое руководство. Оформление дочерних объектов панели
В этом примере показано, как программным способом привязки графического элемента к дочерним элементам указанного <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Пример  
 Для привязки элемента оформления к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:  
  
1.  Объявите новую <xref:System.Windows.Documents.AdornerLayer> и вызовите `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой графических элементов, дочерние элементы которого являются оформляемого элемента.  
  
2.  Перечисление дочерних элементов родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки элемента оформления к каждому дочернему элементу.  
  
 Следующий пример привязывает (показано выше) к дочерним элементам SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)
