---
title: Как Использовать класс FontSizeConverter
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: 625beb06b526e2753abc6f982cf5834bfae1f202
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="24c49-102">Как Использовать класс FontSizeConverter</span><span class="sxs-lookup"><span data-stu-id="24c49-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="24c49-103">Пример</span><span class="sxs-lookup"><span data-stu-id="24c49-103">Example</span></span>  
 <span data-ttu-id="24c49-104">В этом примере показано, как создать экземпляр <xref:System.Windows.FontSizeConverter> и использовать его для изменения размера шрифта.</span><span class="sxs-lookup"><span data-stu-id="24c49-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="24c49-105">В примере определяется пользовательский метод с именем `changeSize` , преобразующий содержимое <xref:System.Windows.Controls.ListBoxItem>, как определено в отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, чтобы экземпляр <xref:System.Double>и более поздней версии в <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="24c49-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="24c49-106">Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.FontSizeConverter> объекта, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру компонента <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="24c49-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="24c49-107">Это значение затем передается обратно в качестве значения <xref:System.Windows.Controls.TextBlock.FontSize%2A> свойство <xref:System.Windows.Controls.TextBlock> элемента.</span><span class="sxs-lookup"><span data-stu-id="24c49-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="24c49-108">Этот пример также определяет второй пользовательский метод, вызываемый `changeFamily`.</span><span class="sxs-lookup"><span data-stu-id="24c49-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="24c49-109">Этот метод преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> для <xref:System.String>, а затем передает это значение <xref:System.Windows.Controls.TextBlock.FontFamily%2A> свойство <xref:System.Windows.Controls.TextBlock> элемент.</span><span class="sxs-lookup"><span data-stu-id="24c49-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="24c49-110">Этот пример не запускается.</span><span class="sxs-lookup"><span data-stu-id="24c49-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="24c49-111">См. также</span><span class="sxs-lookup"><span data-stu-id="24c49-111">See Also</span></span>  
 <xref:System.Windows.FontSizeConverter>
