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
ms.openlocfilehash: b5ba089c671fe54afe1c97da0a7bd786949cb5c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="8ad89-102">Практическое руководство. Создание StackPanel</span><span class="sxs-lookup"><span data-stu-id="8ad89-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="8ad89-103">В этом примере показано, как создать <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="8ad89-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ad89-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8ad89-104">Example</span></span>  
 <span data-ttu-id="8ad89-105">Объект <xref:System.Windows.Controls.StackPanel> позволяет располагать элементы в указанном направлении.</span><span class="sxs-lookup"><span data-stu-id="8ad89-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="8ad89-106">С помощью свойств, которые определены в <xref:System.Windows.Controls.StackPanel>, содержимое может располагаться и по вертикали, который является значением по умолчанию, или по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="8ad89-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="8ad89-107">Следующий пример по вертикали располагаются пять <xref:System.Windows.Controls.TextBlock> элементов управления, каждый с различным <xref:System.Windows.Controls.Border> и <xref:System.Windows.Controls.Border.Background%2A>, с помощью <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="8ad89-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="8ad89-108">Дочерние элементы, которые имеют не указан <xref:System.Windows.FrameworkElement.Width%2A> растягиваются для заполнения родительское окно; Однако дочерние элементы, имеющие указанного <xref:System.Windows.FrameworkElement.Width%2A>, по центру в окне.</span><span class="sxs-lookup"><span data-stu-id="8ad89-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="8ad89-109">По умолчанию направление стека в <xref:System.Windows.Controls.StackPanel> вертикально.</span><span class="sxs-lookup"><span data-stu-id="8ad89-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="8ad89-110">Чтобы контролировать поток содержимого в <xref:System.Windows.Controls.StackPanel>, используйте <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8ad89-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="8ad89-111">Горизонтальное выравнивание можно контролировать с помощью <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8ad89-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ad89-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8ad89-112">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="8ad89-113">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="8ad89-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="8ad89-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="8ad89-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
