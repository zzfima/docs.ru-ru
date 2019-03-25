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
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>Практическое руководство. Определение того, подчеркнута ли ссылка
<xref:System.Windows.Documents.Hyperlink> Объект — это элемент содержимого потока встроенного уровня, позволяющим размещать гиперссылки в содержимом потока. По умолчанию <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.TextDecoration> объекта для отображения подчеркивания. <xref:System.Windows.TextDecoration> объекты могут быть производительность при создании, особенно в том случае, если имеется много <xref:System.Windows.Documents.Hyperlink> объектов. При внесении широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, может потребоваться отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий.  
  
 В следующем примере подчеркивание ссылки «Мой MSN» является динамическим, то есть оно появляется только при <xref:System.Windows.ContentElement.MouseEnter> активируется событие.  
  
  ![Гиперссылки, отображающие TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  
  
  
## <a name="example"></a>Пример  
 В следующем примере разметки демонстрируется <xref:System.Windows.Documents.Hyperlink> определен с подчеркиванием и без него:  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 В следующем образце кода демонстрируется создание подчеркивания для <xref:System.Windows.Documents.Hyperlink> на <xref:System.Windows.ContentElement.MouseEnter> событий и удалите его при <xref:System.Windows.ContentElement.MouseLeave> событий.  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Создание оформления текста](how-to-create-a-text-decoration.md)
