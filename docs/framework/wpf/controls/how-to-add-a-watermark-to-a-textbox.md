---
title: Как выполнить Добавление предела в элемент TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 1ab8c0f9274f4d461c9c2be04ec0aaca5e753c7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531136"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Как выполнить Добавление предела в элемент TextBox
В следующем примере показано, как расширение полезности элемента <xref:System.Windows.Controls.TextBox> , отображая пояснительного фонового изображение внутри <xref:System.Windows.Controls.TextBox> пока пользователь вводит текст, после чего соответствующий образ удаляется. Кроме того фоновое изображение восстанавливается, если пользователь удаляет входные данные. См. рисунок ниже.  
  
 ![TextBox с фоновым изображением](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  Причина, фоновое изображение используется в этом примере вместо применения <xref:System.Windows.Controls.TextBox.Text%2A> свойство <xref:System.Windows.Controls.TextBox>, — что фоновое изображение не будет мешать привязки данных.  
  
## <a name="example"></a>Пример  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
