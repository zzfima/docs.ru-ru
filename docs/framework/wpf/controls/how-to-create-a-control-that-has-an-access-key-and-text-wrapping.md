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
ms.openlocfilehash: bc170334496ca4c2a2028b9c493385674d235ca6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552785"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста
В этом примере показано, как создать элемент управления, который имеет клавишу доступа и поддерживает обтекание текстом. В примере используется <xref:System.Windows.Controls.Label> управления для демонстрации этих понятий.  
  
## <a name="example"></a>Пример  
 **Добавление обтекания текстом для метки**  
  
 <xref:System.Windows.Controls.Label> Управления не поддерживает обтекание текстом. Если нужна метка, которая охватывает несколько строк, то можно вложить другой элемент, который поддерживает обтекание текстом, и поместить этот элемент внутрь метки. В следующем примере показано, как использовать <xref:System.Windows.Controls.TextBlock> для создания метки, которая охватывает несколько строк текста.  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **Добавление клавиши доступа и обтекания текстом в метку**  
  
 Если вам нужна <xref:System.Windows.Controls.Label> , имеет клавишу доступа (назначенную), используйте <xref:System.Windows.Controls.AccessText> элемент, который находится внутри <xref:System.Windows.Controls.Label>.  
  
 Элементы управления, например <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, и <xref:System.Windows.Controls.GroupBox> имеют шаблоны элементов управления по умолчанию. Эти шаблоны содержат <xref:System.Windows.Controls.ContentPresenter>. Одно из свойств, которые можно установить на <xref:System.Windows.Controls.ContentPresenter> является <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= «true», который можно использовать для указания клавиши доступа для элемента управления.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.Label> который имеет клавишу доступа и поддерживает обтекание текстом. Чтобы включить обтекание текстом, в примере задается <xref:System.Windows.Controls.AccessText.TextWrapping%2A> свойство и использует знак подчеркивания для указания клавиши доступа. (Символ, который следует сразу за символом подчеркивания, является клавишей доступа).  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Установка целевого свойства метки](https://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
