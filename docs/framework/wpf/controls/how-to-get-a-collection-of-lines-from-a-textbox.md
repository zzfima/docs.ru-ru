---
title: "Практическое руководство. Получение коллекции строк из элемента TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb771cdb4d12ebaa5160ec16ca57ba6acf011222
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="b7e61-102">Практическое руководство. Получение коллекции строк из элемента TextBox</span><span class="sxs-lookup"><span data-stu-id="b7e61-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="b7e61-103">В этом примере показано, как получить коллекцию строк текста из <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b7e61-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7e61-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b7e61-104">Example</span></span>  
 <span data-ttu-id="b7e61-105">В следующем примере показано простой метод, который принимает <xref:System.Windows.Controls.TextBox> как аргумент и возвращает <xref:System.Collections.Specialized.StringCollection> содержащих строки текста в **TextBox**.</span><span class="sxs-lookup"><span data-stu-id="b7e61-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="b7e61-106"><xref:System.Windows.Controls.TextBox.LineCount%2A> Свойство позволяет определить, сколько строк в настоящее время **TextBox**и <xref:System.Windows.Controls.TextBox.GetLineText%2A> метод затем используется для извлечения каждой строки и добавить его в коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="b7e61-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="b7e61-107">См. также</span><span class="sxs-lookup"><span data-stu-id="b7e61-107">See Also</span></span>  
 [<span data-ttu-id="b7e61-108">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="b7e61-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="b7e61-109">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b7e61-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
