---
title: Практическое руководство. Изменение FlowDirection содержимого программным способом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776562"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Практическое руководство. Изменение FlowDirection содержимого программным способом
В этом примере показано, как программно изменить <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Пример  
 Два <xref:System.Windows.Controls.Button> создаются элементы, каждый из которых представляет одно из возможных значений <xref:System.Windows.FlowDirection>. При нажатии кнопки значение связанного свойства применяется к содержимому <xref:System.Windows.Controls.FlowDocumentReader> с именем `tf1`.  Значение свойства также записывается <xref:System.Windows.Controls.TextBlock> с именем `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Пример  
 События, связанные с нажатием кнопки, определенные выше, обрабатываются в C# файл с выделенным кодом.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
