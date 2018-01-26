---
title: "Практическое руководство. Получение смещения визуального объекта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee18503bdd6100cbe7a62ac70d7ea0848fb124eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-offset-of-a-visual"></a>Практическое руководство. Получение смещения визуального объекта
Этих примерах показано, как получить значение смещения относительно его родительского, любой предков или потомков визуального объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере разметки показан <xref:System.Windows.Controls.TextBlock> , определенный с <xref:System.Windows.FrameworkElement.Margin%2A> значение 4.  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 В следующем примере кода показано, как использовать <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> метод для извлечения смещение <xref:System.Windows.Controls.TextBlock>. Значения смещения содержатся в возвращаемом <xref:System.Windows.Vector> значение.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 Смещение учитывает <xref:System.Windows.FrameworkElement.Margin%2A> значение. В этом случае <xref:System.Windows.Vector.X%2A> равен 4, и <xref:System.Windows.Vector.Y%2A> — 4.  
  
 Возвращаемое значение смещения задается относительно родительского элемента <xref:System.Windows.Media.Visual>. Если вы хотите вернуть значение смещения, который не зависит от родительского элемента <xref:System.Windows.Media.Visual>, используйте <xref:System.Windows.Media.Visual.TransformToAncestor%2A> метод.  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a>Получение смещения относительно предка  
 В следующем примере разметки показан <xref:System.Windows.Controls.TextBlock> , вложенный в двух <xref:System.Windows.Controls.StackPanel> объектов.  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 На следующем рисунке показаны результаты разметки.  
  
 ![Значения смещения объектов](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")  
Вложенные в двух StackPanels TextBlock  
  
 В следующем примере кода показано, как использовать <xref:System.Windows.Media.Visual.TransformToAncestor%2A> метод для извлечения смещение <xref:System.Windows.Controls.TextBlock> относительно содержащего <xref:System.Windows.Window>. Значения смещения содержатся в возвращаемом <xref:System.Windows.Media.GeneralTransform> значение.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 Смещение учитывает <xref:System.Windows.FrameworkElement.Margin%2A> значения для всех объектов класса <xref:System.Windows.Window>. В этом случае <xref:System.Windows.Vector.X%2A> равно 28 (16 + 8 + 4), и <xref:System.Windows.Vector.Y%2A> равно 28.  
  
 Возвращаемое значение смещения задается относительно предка <xref:System.Windows.Media.Visual>. Если вы хотите вернуть значение смещения относительно потомка <xref:System.Windows.Media.Visual>, используйте <xref:System.Windows.Media.Visual.TransformToDescendant%2A> метод.  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a>Получение смещения относительно потомка  
 В следующем примере разметки показан <xref:System.Windows.Controls.TextBlock> содержится в <xref:System.Windows.Controls.StackPanel> объекта.  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 В следующем примере кода показано, как использовать <xref:System.Windows.Media.Visual.TransformToDescendant%2A> метод для извлечения смещение <xref:System.Windows.Controls.StackPanel> относительно его дочерними <xref:System.Windows.Controls.TextBlock>. Значения смещения содержатся в возвращаемом <xref:System.Windows.Media.GeneralTransform> значение.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 Смещение учитывает <xref:System.Windows.FrameworkElement.Margin%2A> значения для всех объектов. В этом случае <xref:System.Windows.Vector.X%2A> равно -4, и <xref:System.Windows.Vector.Y%2A> -4. Значения смещения являются отрицательными, поскольку родительский объект имеет отрицательное значение смещения относительно его дочерний объект.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
