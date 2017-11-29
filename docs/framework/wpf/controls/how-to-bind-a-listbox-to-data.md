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
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="03815-102">Практическое руководство. Привязка элемента ListBox к данным</span><span class="sxs-lookup"><span data-stu-id="03815-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="03815-103">Разработчик приложения можно создать <xref:System.Windows.Controls.ListBox> элементов управления без указания содержимого каждого <xref:System.Windows.Controls.ListBoxItem> отдельно.</span><span class="sxs-lookup"><span data-stu-id="03815-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="03815-104">Привязка данных можно использовать для привязки данных к отдельным элементам.</span><span class="sxs-lookup"><span data-stu-id="03815-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="03815-105">В следующем примере показано, как создать <xref:System.Windows.Controls.ListBox> , заполняющий <xref:System.Windows.Controls.ListBoxItem> элементов с помощью привязки данных в источник данных с именем *цветов*.</span><span class="sxs-lookup"><span data-stu-id="03815-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="03815-106">В этом случае необязательно использовать <xref:System.Windows.Controls.ListBoxItem> теги для указания содержимого каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="03815-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03815-107">Пример</span><span class="sxs-lookup"><span data-stu-id="03815-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="03815-108">См. также</span><span class="sxs-lookup"><span data-stu-id="03815-108">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [<span data-ttu-id="03815-109">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="03815-109">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
