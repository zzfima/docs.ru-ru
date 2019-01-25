---
title: Как выполнить Перевод элемента управления TextBox в режим только для чтения
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517179"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="8de94-102">Как выполнить Перевод элемента управления TextBox в режим только для чтения</span><span class="sxs-lookup"><span data-stu-id="8de94-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="8de94-103">В этом примере показано, как настроить <xref:System.Windows.Controls.TextBox> элемента управления, чтобы запретить пользовательский ввод или изменение.</span><span class="sxs-lookup"><span data-stu-id="8de94-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8de94-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8de94-104">Example</span></span>  
 <span data-ttu-id="8de94-105">Чтобы запретить пользователям изменять содержимое <xref:System.Windows.Controls.TextBox> , назначьте <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> атрибут **true**.</span><span class="sxs-lookup"><span data-stu-id="8de94-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="8de94-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Атрибут влияет только ввод данных пользователем; он не влияет на текст, задайте [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] описание <xref:System.Windows.Controls.TextBox> управления или текст, задать программно с помощью <xref:System.Windows.Controls.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8de94-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="8de94-107">Значение по умолчанию <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> — **false**.</span><span class="sxs-lookup"><span data-stu-id="8de94-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de94-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8de94-108">See also</span></span>
- [<span data-ttu-id="8de94-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="8de94-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="8de94-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8de94-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
