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
ms.workload: dotnet
ms.openlocfilehash: 12d32266bb901f6ce47d19d92d6f0785277aa7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Практическое руководство. Получение коллекции строк из элемента TextBox
В этом примере показано, как получить коллекцию строк текста из <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано простой метод, который принимает <xref:System.Windows.Controls.TextBox> как аргумент и возвращает <xref:System.Collections.Specialized.StringCollection> содержащих строки текста в **TextBox**.  <xref:System.Windows.Controls.TextBox.LineCount%2A> Свойство позволяет определить, сколько строк в настоящее время **TextBox**и <xref:System.Windows.Controls.TextBox.GetLineText%2A> метод затем используется для извлечения каждой строки и добавить его в коллекцию строк.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
