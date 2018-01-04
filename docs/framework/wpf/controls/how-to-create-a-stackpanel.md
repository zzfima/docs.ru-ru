---
title: "Практическое руководство. Создание StackPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9226ac10e4f221cc381b7c59179b2667e20aa757
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-stackpanel"></a>Практическое руководство. Создание StackPanel
В этом примере показано, как создать <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Controls.StackPanel> позволяет располагать элементы в указанном направлении. С помощью свойств, которые определены в <xref:System.Windows.Controls.StackPanel>, содержимое может располагаться и по вертикали, который является значением по умолчанию, или по горизонтали.  
  
 Следующий пример по вертикали располагаются пять <xref:System.Windows.Controls.TextBlock> элементов управления, каждый с различным <xref:System.Windows.Controls.Border> и <xref:System.Windows.Controls.Border.Background%2A>, с помощью <xref:System.Windows.Controls.StackPanel>. Дочерние элементы, которые имеют не указан <xref:System.Windows.FrameworkElement.Width%2A> растягиваются для заполнения родительское окно; Однако дочерние элементы, имеющие указанного <xref:System.Windows.FrameworkElement.Width%2A>, по центру в окне.  
  
 По умолчанию направление стека в <xref:System.Windows.Controls.StackPanel> вертикально. Чтобы контролировать поток содержимого в <xref:System.Windows.Controls.StackPanel>, используйте <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойство. Горизонтальное выравнивание можно контролировать с помощью <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство.  
  
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
 <xref:System.Windows.Controls.StackPanel>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
