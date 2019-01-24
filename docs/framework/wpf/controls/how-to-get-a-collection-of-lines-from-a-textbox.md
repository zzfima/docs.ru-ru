---
title: Как выполнить Получение коллекции строк из элемента TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: a63470c6f0db72340f482bf638910685aa3f461f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561768"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="151b9-102">Как выполнить Получение коллекции строк из элемента TextBox</span><span class="sxs-lookup"><span data-stu-id="151b9-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="151b9-103">В этом примере показано, как получить коллекцию строк текста из <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="151b9-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="151b9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="151b9-104">Example</span></span>  
 <span data-ttu-id="151b9-105">В примере показан простой метод, который принимает <xref:System.Windows.Controls.TextBox> как аргумент и она возвращает <xref:System.Collections.Specialized.StringCollection> содержащих строки текста в **TextBox**.</span><span class="sxs-lookup"><span data-stu-id="151b9-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="151b9-106"><xref:System.Windows.Controls.TextBox.LineCount%2A> Свойство используется для определения, сколько строк находится в данный момент **TextBox**и <xref:System.Windows.Controls.TextBox.GetLineText%2A> метод затем используется для извлечения каждой строки и добавьте его в коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="151b9-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="151b9-107">См. также</span><span class="sxs-lookup"><span data-stu-id="151b9-107">See also</span></span>
- [<span data-ttu-id="151b9-108">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="151b9-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="151b9-109">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="151b9-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
