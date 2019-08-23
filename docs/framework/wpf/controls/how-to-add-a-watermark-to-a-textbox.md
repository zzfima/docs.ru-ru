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
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923579"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="01407-102">Практическое руководство. Добавление водяного знака в элемент TextBox</span><span class="sxs-lookup"><span data-stu-id="01407-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="01407-103">В следующем примере показано, как обеспечить удобство использования <xref:System.Windows.Controls.TextBox> с помощью отображения пояснительного текста в области <xref:System.Windows.Controls.TextBox> до тех пор, пока не будет введен текст, после чего изображение будет удалено.</span><span class="sxs-lookup"><span data-stu-id="01407-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="01407-104">Кроме того, фоновое изображение восстанавливается снова, если пользователь удаляет свои входные данные.</span><span class="sxs-lookup"><span data-stu-id="01407-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="01407-105">См. рисунок ниже.</span><span class="sxs-lookup"><span data-stu-id="01407-105">See illustration below.</span></span>  
  
 <span data-ttu-id="01407-106">![Текстовое поле с фоновым изображением](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="01407-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01407-107">Причина, по которой в этом примере используется фоновое изображение <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox>, вместо того, чтобы просто манипулировать свойством, заключается в том, что фоновое изображение не мешает привязке данных.</span><span class="sxs-lookup"><span data-stu-id="01407-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01407-108">Пример</span><span class="sxs-lookup"><span data-stu-id="01407-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="01407-109">См. также</span><span class="sxs-lookup"><span data-stu-id="01407-109">See also</span></span>

- [<span data-ttu-id="01407-110">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="01407-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="01407-111">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="01407-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
