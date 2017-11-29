---
title: "Практическое руководство. Привязка элемента ListBox к данным"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: deb5e05a7c48f26d0b829ba75b4ae120841e0a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-listbox-to-data"></a>Практическое руководство. Привязка элемента ListBox к данным
Разработчик приложения можно создать <xref:System.Windows.Controls.ListBox> элементов управления без указания содержимого каждого <xref:System.Windows.Controls.ListBoxItem> отдельно. Привязка данных можно использовать для привязки данных к отдельным элементам.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.ListBox> , заполняющий <xref:System.Windows.Controls.ListBoxItem> элементов с помощью привязки данных в источник данных с именем *цветов*. В этом случае необязательно использовать <xref:System.Windows.Controls.ListBoxItem> теги для указания содержимого каждого элемента.  
  
## <a name="example"></a>Пример  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
