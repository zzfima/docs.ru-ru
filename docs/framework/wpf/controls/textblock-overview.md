---
title: Общие сведения о TextBlock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: a3ea656a902f8a112a700667b6e08cae7463f68d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374470"
---
# <a name="textblock-overview"></a>Общие сведения о TextBlock
<xref:System.Windows.Controls.TextBlock> Управления обеспечивает гибкую поддержку текста для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений. Элемент в основном предназначен для базовых сценариев [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], которые не требуют более одного абзаца текста. Он поддерживает ряд свойств, которые обеспечивают точный контроль представления, такие как <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, и <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>. Текстовое содержимое можно добавить с помощью <xref:System.Windows.Controls.TextBlock.Text%2A> свойство. При использовании в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] содержимое между открывающим и закрывающим тегами неявно добавляется в качестве текста элемента.  
  
 Объект <xref:System.Windows.Controls.TextBlock> элемент могут создаваться очень просто с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 Аналогично, использование <xref:System.Windows.Controls.TextBlock> элемента в коде приложения относительно прост.  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Label>
