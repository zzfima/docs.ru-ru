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
ms.openlocfilehash: a142604fdb36ec6f85e9411b37077bfffff587d4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363921"
---
# <a name="how-to-create-a-text-decoration"></a>Практическое руководство. Создание оформления текста
Объект <xref:System.Windows.TextDecoration> объект представляет визуальную орнаментацию, можно добавить в текст. There are four types of text decorations: underline, baseline, strikethrough, and overline. Пример расположения оформления текста относительно текста.  
  
 ![Схема расположений украшений текста](./media/textdecoration01.gif "TextDecoration01")  
Пример типов оформления текста  
  
 Чтобы добавить оформление текста в текст, создайте <xref:System.Windows.TextDecoration> объекта и измените его свойства. Используйте <xref:System.Windows.TextDecoration.Location%2A> свойство, чтобы указать, где отображается оформления текста, такие как подчеркивание. Используйте <xref:System.Windows.TextDecoration.Pen%2A> свойство, чтобы указать внешний вид оформления текста, например сплошная заливка или цвет градиента. Если не указать значение для <xref:System.Windows.TextDecoration.Pen%2A> свойство, оформление будет по умолчанию цвет текста. После определения <xref:System.Windows.TextDecoration> объекта, добавьте ее в <xref:System.Windows.TextDecorations> коллекции объекта нужный текст.  
  
 Пример с кисти линейного градиента и штрихового пера оформление текста.  
  
 ![Украшение текста с подчеркиванием линейным градиентом](./media/textdecoration02.png "TextDecoration02")  
Пример подчеркивания, таким образом, с помощью линейного градиента кисти и штриховой пера  
  
 <xref:System.Windows.Documents.Hyperlink> Объект — это элемент содержимого потока встроенного уровня, позволяющим размещать гиперссылки в содержимом потока. По умолчанию <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.TextDecoration> объекта для отображения подчеркивания. <xref:System.Windows.TextDecoration> объекты могут быть производительность при создании, особенно в том случае, если имеется много <xref:System.Windows.Documents.Hyperlink> объектов. При внесении широкое использование <xref:System.Windows.Documents.Hyperlink> элементов, может потребоваться отображать подчеркивание только при возникновении события, такие как <xref:System.Windows.ContentElement.MouseEnter> событий.  
  
 В следующем примере подчеркивание ссылки «Мой MSN» является динамическим — оно появляется только при <xref:System.Windows.ContentElement.MouseEnter> активируется событие.  
  
 ![Гиперссылки, отображение TextDecorations](./media/textdecoration03.png "TextDecoration03")  
Гиперссылки, определенные с помощью TextDecorations  
  
 Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода подчеркивание текста использует шрифт по умолчанию.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 В следующем примере кода подчеркивание текста создается с Одноцветная кисть для пера.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 В следующем примере кода подчеркивание текста создается с помощью кисти линейного градиента для пунктирного пера.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Определение того, подчеркнута ли ссылка](how-to-specify-whether-a-hyperlink-is-underlined.md)
