---
title: "Практическое руководство. Извлечение выделенного текста"
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
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d5e1c362c02d2d1d9e1840ea2a55df6875a80ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-a-text-selection"></a>Практическое руководство. Извлечение выделенного текста
В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.SelectedText%2A> свойства, чтобы получить текст, который пользователь выбрал в <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере показано определение <xref:System.Windows.Controls.TextBox> управления, который содержит некоторый текст, чтобы выбрать, и <xref:System.Windows.Controls.Button> управления с заданными <xref:System.Windows.Controls.Button.OnClick%2A> метод.  
  
 В этом примере кнопка со связанным <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий используется для извлечения выбранного текста. Когда пользователь нажимает кнопку, <xref:System.Windows.Controls.Button.OnClick%2A> метод копирует любой выделенный текст в текстовом поле в строку. Обстоятельствах для, на которые выбранный текст является извлечения (нажатию кнопки), также действие, выполняемое с выделенным (копирование выделенного текста в строку), можно легко изменить для размещения разнообразных сценариях.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] примере <xref:System.Windows.Controls.Button.OnClick%2A> обработчик событий для кнопки, определенные в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для этого примера.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
