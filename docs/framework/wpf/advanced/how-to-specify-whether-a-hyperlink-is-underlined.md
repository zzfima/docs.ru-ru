---
title: Практическое руководство. Определение того, подчеркнута ли ссылка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 1968e1b2730f08eb76670a477f1d2bdb0a9140bf
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408708"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="b4da9-102">Практическое руководство. Определение того, подчеркнута ли ссылка</span><span class="sxs-lookup"><span data-stu-id="b4da9-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="b4da9-103"><xref:System.Windows.Documents.Hyperlink> Объект — это элемент содержимого потока встроенного уровня, позволяющим размещать гиперссылки в содержимом потока.</span><span class="sxs-lookup"><span data-stu-id="b4da9-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="b4da9-104">По умолчанию <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.TextDecoration> объекта для отображения подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="b4da9-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="b4da9-105"><xref:System.Windows.TextDecoration> объекты могут быть производительность при создании, особенно в том случае, если имеется много <xref:System.Windows.Documents.Hyperlink> объектов.</span><span class="sxs-lookup"><span data-stu-id="b4da9-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="b4da9-106">При внесении широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, может потребоваться отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий.</span><span class="sxs-lookup"><span data-stu-id="b4da9-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="b4da9-107">В следующем примере подчеркивание ссылки «Мой MSN» является динамическим, то есть оно появляется только при <xref:System.Windows.ContentElement.MouseEnter> активируется событие.</span><span class="sxs-lookup"><span data-stu-id="b4da9-107">In the following example, the underline for the "My MSN" link is dynamic, that is, it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
  ![Гиперссылки, отображающие TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  
  
  
## <a name="example"></a><span data-ttu-id="b4da9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b4da9-109">Example</span></span>  
 <span data-ttu-id="b4da9-110">В следующем примере разметки демонстрируется <xref:System.Windows.Documents.Hyperlink> определен с подчеркиванием и без него:</span><span class="sxs-lookup"><span data-stu-id="b4da9-110">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="b4da9-111">В следующем образце кода демонстрируется создание подчеркивания для <xref:System.Windows.Documents.Hyperlink> на <xref:System.Windows.ContentElement.MouseEnter> событий и удалите его при <xref:System.Windows.ContentElement.MouseLeave> событий.</span><span class="sxs-lookup"><span data-stu-id="b4da9-111">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="b4da9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b4da9-112">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="b4da9-113">Улучшение производительности приложений WPF</span><span class="sxs-lookup"><span data-stu-id="b4da9-113">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="b4da9-114">Создание оформления текста</span><span class="sxs-lookup"><span data-stu-id="b4da9-114">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)
