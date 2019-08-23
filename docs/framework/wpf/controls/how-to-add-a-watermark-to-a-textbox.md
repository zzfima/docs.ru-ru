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
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Практическое руководство. Добавление водяного знака в элемент TextBox
В следующем примере показано, как обеспечить удобство использования <xref:System.Windows.Controls.TextBox> с помощью отображения пояснительного текста в области <xref:System.Windows.Controls.TextBox> до тех пор, пока не будет введен текст, после чего изображение будет удалено. Кроме того, фоновое изображение восстанавливается снова, если пользователь удаляет свои входные данные. См. рисунок ниже.  
  
 ![Текстовое поле с фоновым изображением](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
> Причина, по которой в этом примере используется фоновое изображение <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox>, вместо того, чтобы просто манипулировать свойством, заключается в том, что фоновое изображение не мешает привязке данных.  
  
## <a name="example"></a>Пример  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
