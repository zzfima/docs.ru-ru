---
title: Практическое руководство. Добавление водяного знака в элемент TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: ef2536f03ba6ed08e27d2fcf30cd1f72df2cf460
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142419"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="cc53d-102">Практическое руководство. Добавление водяного знака в элемент TextBox</span><span class="sxs-lookup"><span data-stu-id="cc53d-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="cc53d-103">В следующем примере показано, как расширение полезности элемента <xref:System.Windows.Controls.TextBox> , отображая пояснительного фонового изображение внутри <xref:System.Windows.Controls.TextBox> пока пользователь вводит текст, после чего соответствующий образ удаляется.</span><span class="sxs-lookup"><span data-stu-id="cc53d-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="cc53d-104">Кроме того фоновое изображение восстанавливается, если пользователь удаляет входные данные.</span><span class="sxs-lookup"><span data-stu-id="cc53d-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="cc53d-105">См. рисунок ниже.</span><span class="sxs-lookup"><span data-stu-id="cc53d-105">See illustration below.</span></span>  
  
 <span data-ttu-id="cc53d-106">![TextBox с фоновым изображением](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="cc53d-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc53d-107">Причина, фоновое изображение используется в этом примере вместо применения <xref:System.Windows.Controls.TextBox.Text%2A> свойство <xref:System.Windows.Controls.TextBox>, — что фоновое изображение не будет мешать привязки данных.</span><span class="sxs-lookup"><span data-stu-id="cc53d-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc53d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="cc53d-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cc53d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cc53d-109">See also</span></span>

- [<span data-ttu-id="cc53d-110">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="cc53d-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="cc53d-111">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="cc53d-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
