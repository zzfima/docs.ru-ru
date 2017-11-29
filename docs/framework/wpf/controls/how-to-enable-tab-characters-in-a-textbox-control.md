---
title: "Практическое руководство. Включение знаков табуляции в элементе управления TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc77668d9544cb37a8c9d1fcbdc3ed0351bc9eef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>Практическое руководство. Включение знаков табуляции в элементе управления TextBox
В этом примере показано включение принятия знаков табуляции в качестве обычных входных данных в <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Включение принятия знаков табуляции в качестве входных данных в <xref:System.Windows.Controls.TextBox> установите <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> атрибут **true**.  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
