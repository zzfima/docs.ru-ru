---
title: "Практическое руководство. Размещение дочерних элементов Grid"
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
helpviewer_keywords: Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Практическое руководство. Размещение дочерних элементов Grid
В этом примере показано, как использовать команду get и задать методы, определенные на <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется родительским <xref:System.Windows.Controls.Grid> элемент (`grid1`), содержит три столбца и три строки. Дочерний элемент <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) добавляется <xref:System.Windows.Controls.Grid> в нулевой позиции столбца, строка нулевой позиции. <xref:System.Windows.Controls.Button>элементы, которые представляют методы, которые могут быть вызваны для изменения положения <xref:System.Windows.Shapes.Rectangle> элемент в пределах <xref:System.Windows.Controls.Grid>. Когда пользователь нажимает кнопку, активируется связанный метод.  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 В следующем примере кода обрабатывает методы, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызова события. Пример записывает эти вызовы методов в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы получения для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Grid>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
