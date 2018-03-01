---
title: "Практическое руководство. Определение того, подчеркнута ли ссылка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 24c3cc1bba4fd12d4a0f2ad02fa0c1b52b124381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="dc616-102">Практическое руководство. Определение того, подчеркнута ли ссылка</span><span class="sxs-lookup"><span data-stu-id="dc616-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="dc616-103"><xref:System.Windows.Documents.Hyperlink> Объект является элемент содержимого потока встроенного уровня, позволяющий размещать гиперссылки в содержимом потока.</span><span class="sxs-lookup"><span data-stu-id="dc616-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="dc616-104">По умолчанию <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.TextDecoration> объекта для отображения подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="dc616-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="dc616-105"><xref:System.Windows.TextDecoration>объекты могут быть производительность при создании, особенно в том случае, если имеется много <xref:System.Windows.Documents.Hyperlink> объектов.</span><span class="sxs-lookup"><span data-stu-id="dc616-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="dc616-106">Если предусматривают широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, может потребоваться отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий.</span><span class="sxs-lookup"><span data-stu-id="dc616-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="dc616-107">В следующем примере подчеркивание ссылки «Мой MSN» является динамическим — оно появляется только при <xref:System.Windows.ContentElement.MouseEnter> события.</span><span class="sxs-lookup"><span data-stu-id="dc616-107">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="dc616-108">![Гиперссылки, отображающие TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="dc616-108">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="dc616-109">Гиперссылки, определенные с TextDecorations</span><span class="sxs-lookup"><span data-stu-id="dc616-109">Hyperlinks defined with TextDecorations</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc616-110">Пример</span><span class="sxs-lookup"><span data-stu-id="dc616-110">Example</span></span>  
 <span data-ttu-id="dc616-111">В следующем примере демонстрируется разметки <xref:System.Windows.Documents.Hyperlink> определен с подчеркиванием и без него:</span><span class="sxs-lookup"><span data-stu-id="dc616-111">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="dc616-112">В следующем образце кода демонстрируется создание подчеркивания для <xref:System.Windows.Documents.Hyperlink> на <xref:System.Windows.ContentElement.MouseEnter> события и удалите его при <xref:System.Windows.ContentElement.MouseLeave> события.</span><span class="sxs-lookup"><span data-stu-id="dc616-112">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="dc616-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dc616-113">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="dc616-114">Улучшение производительности приложений WPF</span><span class="sxs-lookup"><span data-stu-id="dc616-114">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="dc616-115">Создание оформления текста</span><span class="sxs-lookup"><span data-stu-id="dc616-115">Create a Text Decoration</span></span>](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
