---
title: "Практическое руководство. Создание и использование объекта GridLengthConverter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 300916ec102682e1d886d43fbe70eeaf088d6454
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Практическое руководство. Создание и использование объекта GridLengthConverter
## <a name="example"></a>Пример  
 В следующем примере показано создание и использование экземпляра <xref:System.Windows.GridLengthConverter>. В примере определяется пользовательский метод с именем `changeCol`, который передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.GridLengthConverter> , преобразующий <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру компонента <xref:System.Windows.GridLength>. Преобразованное значение затем передается обратно в качестве значения <xref:System.Windows.Controls.ColumnDefinition.Width%2A> свойство <xref:System.Windows.Controls.ColumnDefinition> элемента.  
  
 В примере также определяется второй пользовательский метод с именем `changeColVal`. Этот пользовательский метод преобразует <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> из <xref:System.Windows.Controls.Slider> для <xref:System.String> и затем передает значение обратно <xref:System.Windows.Controls.ColumnDefinition> как <xref:System.Windows.Controls.ColumnDefinition.Width%2A> элемента.  
  
 Обратите внимание, что отдельный [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл определяет содержимое <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.GridLengthConverter>  
 <xref:System.Windows.GridLength>
