---
title: Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 8343c660ddeb5487f46e87534e555936d1b86371
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста
В этом примере показано, как создать элемент управления, который имеет клавишу доступа и поддерживает обтекание текстом. В этом примере <xref:System.Windows.Controls.Label> управления для иллюстрации этих основных понятий.  
  
## <a name="example"></a>Пример  
 **Добавление обтекания текстом для метки**  
  
 <xref:System.Windows.Controls.Label> Управления не поддерживает перенос текста. Если нужна метка, которая охватывает несколько строк, то можно вложить другой элемент, который поддерживает обтекание текстом, и поместить этот элемент внутрь метки. В следующем примере показано, как использовать <xref:System.Windows.Controls.TextBlock> для создания метки, которая содержит несколько строк текста.  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **Добавление клавиши доступа и обтекания текстом в метку**  
  
 Если вам требуется <xref:System.Windows.Controls.Label> , содержащий ключ доступа (назначенную), используйте <xref:System.Windows.Controls.AccessText> элемент, находящийся внутри <xref:System.Windows.Controls.Label>.  
  
 Элементы управления, например <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, и <xref:System.Windows.Controls.GroupBox> есть шаблона элемента управления по умолчанию. Эти шаблоны содержат <xref:System.Windows.Controls.ContentPresenter>. Одно из свойств, которые можно установить на <xref:System.Windows.Controls.ContentPresenter> — <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= «true», который можно использовать для указания клавиши доступа для элемента управления.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.Label> , имеет клавишу доступа и поддерживает перенос текста. Чтобы включить перенос текста, в примере задается <xref:System.Windows.Controls.AccessText.TextWrapping%2A> свойства и используется знак подчеркивания для указания ключа доступа. (Символ, который следует сразу за символом подчеркивания, является клавишей доступа).  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Установка целевого свойства метки](http://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
