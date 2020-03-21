---
title: Практическое руководство. Создание оформления текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185923"
---
# <a name="how-to-create-a-text-decoration"></a>Практическое руководство. Создание оформления текста
Объект <xref:System.Windows.TextDecoration> представляет собой визуальное украшение, что можно добавить в текст. Существует четыре типа текстовых декораций: подчеркивание, базовый, ударный и оверлайн. В следующем примере показаны расположение текстовых декораций относительно текста.  
  
 ![Диаграмма типов оформления текста](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 Чтобы добавить текстовое оформление в текст, создайте <xref:System.Windows.TextDecoration> объект и измените его свойства. Используйте <xref:System.Windows.TextDecoration.Location%2A> свойство, чтобы указать, где появляется текстовое украшение, например, подчеркивание. Используйте <xref:System.Windows.TextDecoration.Pen%2A> свойство, чтобы указать внешний вид текстового оформления, например, цельного цвета заполнения или градиента. Если вы не указываете <xref:System.Windows.TextDecoration.Pen%2A> значение для свойства, украшения по умолчанию по умолчанию к тому же цвету, как текст. После того как <xref:System.Windows.TextDecoration> вы определили <xref:System.Windows.TextDecorations> объект, добавьте его в коллекцию желаемого объекта текста.  
  
 Ниже приводится текстовое украшение, которое было оформлено с линейной градиентной кистью и пунктирной ручкой.  
  
 ![Украшение текста с подчеркиванием линейным градиентом](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 Объект <xref:System.Windows.Documents.Hyperlink> представляет собой элемент содержимого потока уровня, который позволяет размещать гиперссылки в содержимом потока. По умолчанию <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.TextDecoration> используется объект для отображения подчеркивания. <xref:System.Windows.TextDecoration>объекты могут быть интенсивными для мгновенного выполнения <xref:System.Windows.Documents.Hyperlink> объектов, особенно если у вас есть много объектов. Если вы широко <xref:System.Windows.Documents.Hyperlink> используете элементы, вы можете рассмотреть возможность показа подчеркивания только при запуске события, например <xref:System.Windows.ContentElement.MouseEnter> события.  
  
 В следующем примере подчеркивание для ссылки "My MSN" <xref:System.Windows.ContentElement.MouseEnter> является динамическим — оно появляется только при срабатывании события.  
  
 ![Гиперссылки, отображающие TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода в выделении текста используется значение шрифта по умолчанию.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 В следующем примере кода, подчеркивая текст украшения создается с твердой цветовой кистью для пера.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 В следующем примере кода, подчеркивающее текстовое украшение создается с линейной градиентной кистью для пунктирной ручки.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md)
