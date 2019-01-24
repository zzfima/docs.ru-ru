---
title: Как выполнить Создание и использование объекта GridLengthConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: b5ab15df4aaf5f6c4ba7bc7a4b36cc5e122b1320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562065"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Как выполнить Создание и использование объекта GridLengthConverter
## <a name="example"></a>Пример  
 В следующем примере показано, как создать и использовать экземпляр <xref:System.Windows.GridLengthConverter>. В примере определяется пользовательский метод с именем `changeCol`, который передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.GridLengthConverter> , преобразующий <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Windows.GridLength>. Преобразованное значение затем передается обратно в качестве значения <xref:System.Windows.Controls.ColumnDefinition.Width%2A> свойство <xref:System.Windows.Controls.ColumnDefinition> элемент.  
  
 В примере также определяется второй пользовательский метод с именем `changeColVal`. Этот пользовательский метод преобразует <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> из <xref:System.Windows.Controls.Slider> для <xref:System.String> и затем передает значение обратно <xref:System.Windows.Controls.ColumnDefinition> как <xref:System.Windows.Controls.ColumnDefinition.Width%2A> элемента.  
  
 Обратите внимание, что отдельный [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл определяет содержание <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
