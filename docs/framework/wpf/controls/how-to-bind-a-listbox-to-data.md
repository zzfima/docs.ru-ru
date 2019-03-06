---
title: Практическое руководство. Привязка элемента ListBox к данным
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 2cbcb0fb859605c33e2d92559b4a47aa1725472c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372885"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="99a76-102">Практическое руководство. Привязка элемента ListBox к данным</span><span class="sxs-lookup"><span data-stu-id="99a76-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="99a76-103">Разработчик приложения можно создать <xref:System.Windows.Controls.ListBox> элементы управления без указания содержимого каждого <xref:System.Windows.Controls.ListBoxItem> отдельно.</span><span class="sxs-lookup"><span data-stu-id="99a76-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="99a76-104">Можно использовать привязку данных для привязки данных для отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="99a76-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="99a76-105">В следующем примере показано, как создать <xref:System.Windows.Controls.ListBox> , заполняющий <xref:System.Windows.Controls.ListBoxItem> элементов путем привязки данных к источнику данных с именем *цвета*.</span><span class="sxs-lookup"><span data-stu-id="99a76-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="99a76-106">В этом случае необязательно использовать <xref:System.Windows.Controls.ListBoxItem> теги для указания содержимого каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="99a76-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99a76-107">Пример</span><span class="sxs-lookup"><span data-stu-id="99a76-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="99a76-108">См. также</span><span class="sxs-lookup"><span data-stu-id="99a76-108">See also</span></span>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="99a76-109">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="99a76-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
