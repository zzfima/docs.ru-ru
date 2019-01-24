---
title: Как выполнить Использование пользовательского контекстного меню с элементом TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 5b1b0ea569831361c4680102e8229fe3755bffda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742345"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>Как выполнить Использование пользовательского контекстного меню с элементом TextBox
В этом примере показано, как определить и реализовать простое пользовательское контекстное меню для <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере определяется <xref:System.Windows.Controls.TextBox> элемент управления, который включает в себя пользовательского контекстного меню.  
  
 В контекстном меню определяется с помощью <xref:System.Windows.Controls.ContextMenu> элемент.  Само контекстное меню состоит из ряда <xref:System.Windows.Controls.MenuItem> элементов и <xref:System.Windows.Controls.Separator> элементов.  Каждый <xref:System.Windows.Controls.MenuItem> элемент определяет команду в контекстном меню; <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> атрибут определяет отображаемый текст для команды меню и <xref:System.Windows.Controls.MenuItem.Click> атрибут задает метод обработчика для каждого пункта меню.  <xref:System.Windows.Controls.Separator> Элемент просто отображает разделяющую строку между предыдущей и последующей пунктов.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, код реализации предыдущего определения контекстного меню, а также код, который включает и отключает контекстного меню.  <xref:System.Windows.Controls.ContextMenu.Opened> Событие используется для динамического включения или отключения определенных команд в зависимости от текущего состояния <xref:System.Windows.Controls.TextBox>.  
  
 Чтобы восстановить контекстное меню по умолчанию, используйте <xref:System.Windows.DependencyObject.ClearValue%2A> метод, чтобы удалить значение <xref:System.Windows.FrameworkElement.ContextMenu%2A> свойства.  Чтобы полностью отключить контекстное меню, задайте <xref:System.Windows.FrameworkElement.ContextMenu%2A> свойство пустую ссылку (`Nothing` в Visual Basic).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>См. также
- [Использование проверки орфографии с помощью контекстного меню](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)
- [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
