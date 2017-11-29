---
title: "Практическое руководство. Использование пользовательского контекстного меню с элементом TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc2bb5645467e785626ad8e2a4624335d5d110fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="eac06-102">Практическое руководство. Использование пользовательского контекстного меню с элементом TextBox</span><span class="sxs-lookup"><span data-stu-id="eac06-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="eac06-103">В этом примере показано, как определить и реализовать простое пользовательское контекстное меню для <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="eac06-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eac06-104">Пример</span><span class="sxs-lookup"><span data-stu-id="eac06-104">Example</span></span>  
 <span data-ttu-id="eac06-105">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере определяется <xref:System.Windows.Controls.TextBox> элемент управления, который включает в себя пользовательское контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="eac06-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="eac06-106">В контекстном меню определяется с помощью <xref:System.Windows.Controls.ContextMenu> элемента.</span><span class="sxs-lookup"><span data-stu-id="eac06-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="eac06-107">Само контекстное меню состоит из ряда <xref:System.Windows.Controls.MenuItem> элементы и <xref:System.Windows.Controls.Separator> элементы.</span><span class="sxs-lookup"><span data-stu-id="eac06-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="eac06-108">Каждый <xref:System.Windows.Controls.MenuItem> элемент определяет команду в контекстном меню; <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> атрибут определяет отображаемый текст для команды меню и <xref:System.Windows.Controls.MenuItem.Click> атрибут задает метод обработчика для каждого пункта меню.</span><span class="sxs-lookup"><span data-stu-id="eac06-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="eac06-109"><xref:System.Windows.Controls.Separator> Элемент просто отображает разделяющую строку между элементами меню предыдущих и последующих.</span><span class="sxs-lookup"><span data-stu-id="eac06-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="eac06-110">Пример</span><span class="sxs-lookup"><span data-stu-id="eac06-110">Example</span></span>  
 <span data-ttu-id="eac06-111">В следующем примере показано, код реализации предыдущего определения контекстного меню, а также код, который включает и отключает контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="eac06-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="eac06-112"><xref:System.Windows.Controls.ContextMenu.Opened> Событие используется для динамического включения или отключения определенных команд в зависимости от текущего состояния <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="eac06-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="eac06-113">Чтобы восстановить контекстное меню по умолчанию, используйте <xref:System.Windows.DependencyObject.ClearValue%2A> метод, чтобы удалить значение <xref:System.Windows.FrameworkElement.ContextMenu%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="eac06-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="eac06-114">Чтобы полностью отключить контекстное меню, установите <xref:System.Windows.FrameworkElement.ContextMenu%2A> свойству пустую ссылку (`Nothing` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="eac06-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="eac06-115">См. также</span><span class="sxs-lookup"><span data-stu-id="eac06-115">See Also</span></span>  
 [<span data-ttu-id="eac06-116">Использование проверки орфографии с помощью контекстного меню</span><span class="sxs-lookup"><span data-stu-id="eac06-116">Use Spell Checking with a Context Menu</span></span>](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [<span data-ttu-id="eac06-117">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="eac06-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="eac06-118">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="eac06-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
