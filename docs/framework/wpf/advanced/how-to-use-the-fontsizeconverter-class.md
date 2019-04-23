---
title: Практическое руководство. Использование класса FontSizeConverter
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: f33a297ae07d5509d2b4d9a98636086ac433a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979361"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="09937-102">Практическое руководство. Использование класса FontSizeConverter</span><span class="sxs-lookup"><span data-stu-id="09937-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="09937-103">Пример</span><span class="sxs-lookup"><span data-stu-id="09937-103">Example</span></span>  
 <span data-ttu-id="09937-104">В этом примере показано, как создать экземпляр <xref:System.Windows.FontSizeConverter> и использовать его для изменения размера шрифта.</span><span class="sxs-lookup"><span data-stu-id="09937-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="09937-105">В примере определяется пользовательский метод с именем `changeSize` , преобразующий содержимое <xref:System.Windows.Controls.ListBoxItem>, как определено в отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, чтобы экземпляр <xref:System.Double>и более поздних версий в <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="09937-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="09937-106">Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.FontSizeConverter> объект, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="09937-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="09937-107">Это значение затем передается обратно в качестве значения <xref:System.Windows.Controls.TextBlock.FontSize%2A> свойство <xref:System.Windows.Controls.TextBlock> элемент.</span><span class="sxs-lookup"><span data-stu-id="09937-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="09937-108">В этом примере также определяется второй пользовательский метод, вызываемый `changeFamily`.</span><span class="sxs-lookup"><span data-stu-id="09937-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="09937-109">Этот метод преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> для <xref:System.String>, а затем передает это значение <xref:System.Windows.Controls.TextBlock.FontFamily%2A> свойство <xref:System.Windows.Controls.TextBlock> элемент.</span><span class="sxs-lookup"><span data-stu-id="09937-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="09937-110">Этот пример не запускается.</span><span class="sxs-lookup"><span data-stu-id="09937-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="09937-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09937-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
