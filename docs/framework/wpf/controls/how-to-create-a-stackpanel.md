---
title: Практическое руководство. Создание StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121814"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="3beb1-102">Практическое руководство. Создание StackPanel</span><span class="sxs-lookup"><span data-stu-id="3beb1-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="3beb1-103">В этом примере показано, как создать <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="3beb1-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3beb1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3beb1-104">Example</span></span>  
 <span data-ttu-id="3beb1-105">Объект <xref:System.Windows.Controls.StackPanel> позволяет располагать элементы в указанном направлении.</span><span class="sxs-lookup"><span data-stu-id="3beb1-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="3beb1-106">С помощью свойств, которые определены на <xref:System.Windows.Controls.StackPanel>, содержимое может располагаться как по вертикали, которое является значением по умолчанию, горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="3beb1-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="3beb1-107">Следующий пример по вертикали располагаются пять <xref:System.Windows.Controls.TextBlock> элементы управления, с разными <xref:System.Windows.Controls.Border> и <xref:System.Windows.Controls.Border.Background%2A>, с помощью <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="3beb1-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="3beb1-108">Дочерние элементы, у которых нет указанного <xref:System.Windows.FrameworkElement.Width%2A> растягиваются для заполнения родительского окна; Однако дочерние элементы, имеющие указанный <xref:System.Windows.FrameworkElement.Width%2A>, выравнивается по центру окна.</span><span class="sxs-lookup"><span data-stu-id="3beb1-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="3beb1-109">По умолчанию направление стека в <xref:System.Windows.Controls.StackPanel> является вертикальным.</span><span class="sxs-lookup"><span data-stu-id="3beb1-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="3beb1-110">Для управления потоком содержимого в <xref:System.Windows.Controls.StackPanel>, используйте <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3beb1-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="3beb1-111">Горизонтальное выравнивание можно контролировать с помощью <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3beb1-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3beb1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3beb1-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="3beb1-113">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="3beb1-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="3beb1-114">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="3beb1-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
