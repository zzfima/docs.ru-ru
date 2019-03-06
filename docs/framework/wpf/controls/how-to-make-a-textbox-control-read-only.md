---
title: Практическое руководство. Перевод элемента управления TextBox в режим только для чтения
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3784471020210f995c8bb0a377d56a2466d97da1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364546"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Практическое руководство. Перевод элемента управления TextBox в режим только для чтения
В этом примере показано, как настроить <xref:System.Windows.Controls.TextBox> элемента управления, чтобы запретить пользовательский ввод или изменение.  
  
## <a name="example"></a>Пример  
 Чтобы запретить пользователям изменять содержимое <xref:System.Windows.Controls.TextBox> , назначьте <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> атрибут **true**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Атрибут влияет только ввод данных пользователем; он не влияет на текст, задайте [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] описание <xref:System.Windows.Controls.TextBox> управления или текст, задать программно с помощью <xref:System.Windows.Controls.TextBox.Text%2A> свойство.  
  
 Значение по умолчанию <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> — **false**.  
  
## <a name="see-also"></a>См. также
- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
