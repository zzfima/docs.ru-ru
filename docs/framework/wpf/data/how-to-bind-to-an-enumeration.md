---
title: "Практическое руководство. Привязка к перечислению"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31fb9adbda47514e5405d465c0b5e2493b966d8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="2b6f6-102">Практическое руководство. Привязка к перечислению</span><span class="sxs-lookup"><span data-stu-id="2b6f6-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="2b6f6-103">В этом примере показано, как выполнить привязку к перечислению путем привязки к методу GetValues перечисления.</span><span class="sxs-lookup"><span data-stu-id="2b6f6-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b6f6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2b6f6-104">Example</span></span>  
 <span data-ttu-id="2b6f6-105">В следующем примере <xref:System.Windows.Controls.ListBox> отображает список <xref:System.Windows.HorizontalAlignment> значения перечисления с помощью привязки данных.</span><span class="sxs-lookup"><span data-stu-id="2b6f6-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="2b6f6-106"><xref:System.Windows.Controls.ListBox> И <xref:System.Windows.Controls.Button> связаны таким образом, вы можете изменить <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение свойства <xref:System.Windows.Controls.Button> , выбрав значение в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="2b6f6-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="2b6f6-107">См. также</span><span class="sxs-lookup"><span data-stu-id="2b6f6-107">See Also</span></span>  
 [<span data-ttu-id="2b6f6-108">Создание привязки к методу</span><span class="sxs-lookup"><span data-stu-id="2b6f6-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="2b6f6-109">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="2b6f6-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="2b6f6-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="2b6f6-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
