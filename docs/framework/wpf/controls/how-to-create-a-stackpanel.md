---
title: Как выполнить Создание StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: 20e2b21b10129c096398606501768a7ace0617fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674236"
---
# <a name="how-to-create-a-stackpanel"></a>Как выполнить Создание StackPanel
В этом примере показано, как создать <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Controls.StackPanel> позволяет располагать элементы в указанном направлении. С помощью свойств, которые определены на <xref:System.Windows.Controls.StackPanel>, содержимое может располагаться как по вертикали, которое является значением по умолчанию, горизонтально или вертикально.  
  
 Следующий пример по вертикали располагаются пять <xref:System.Windows.Controls.TextBlock> элементы управления, с разными <xref:System.Windows.Controls.Border> и <xref:System.Windows.Controls.Border.Background%2A>, с помощью <xref:System.Windows.Controls.StackPanel>. Дочерние элементы, у которых нет указанного <xref:System.Windows.FrameworkElement.Width%2A> растягиваются для заполнения родительского окна; Однако дочерние элементы, имеющие указанный <xref:System.Windows.FrameworkElement.Width%2A>, выравнивается по центру окна.  
  
 По умолчанию направление стека в <xref:System.Windows.Controls.StackPanel> является вертикальным. Для управления потоком содержимого в <xref:System.Windows.Controls.StackPanel>, используйте <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойство. Горизонтальное выравнивание можно контролировать с помощью <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.StackPanel>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
