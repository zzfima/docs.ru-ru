---
title: Практическое руководство. Совместное использование свойств размера между сетками
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: a85c0c36ef99e6501afddaca7f26acd2928da1ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550869"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Практическое руководство. Совместное использование свойств размера между сетками
В этом примере показано применение общего доступа к данным размера столбцов и строк для <xref:System.Windows.Controls.Grid> элементов, чтобы сохранить согласованное изменение размеров.  
  
## <a name="example"></a>Пример  
 Приведенный ниже представлены два <xref:System.Windows.Controls.Grid> элементы как дочерние элементы родительского <xref:System.Windows.Controls.DockPanel>. <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Присоединенное свойство <xref:System.Windows.Controls.Grid> определенные в родительском <xref:System.Windows.Controls.DockPanel>.  
  
 В примере значение свойства управляется с помощью двух <xref:System.Windows.Controls.Button> элементов; каждый элемент представляет один из значений свойства типа Boolean. Когда <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> имеет значение `true`, каждый член столбца или строки <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> использует сведения о размере, независимо от содержимого строки или столбца.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 В следующем примере кода обрабатывает методы, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывает событие. В примере записываются результаты этих вызовов <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы получения для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
