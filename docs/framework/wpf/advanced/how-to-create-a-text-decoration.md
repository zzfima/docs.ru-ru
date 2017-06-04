---
title: "Практическое руководство. Создание оформления текста | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "тип направляющей"
  - "шрифты, направляющая"
  - "шрифты, надчеркивание"
  - "шрифты, зачеркивание"
  - "шрифты, подчеркивание"
  - "тип надчеркивания"
  - "тип зачеркивания"
  - "текст, декорирование"
  - "оформление, оформление текста"
  - "тип подчеркивания"
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание оформления текста
Объект <xref:System.Windows.TextDecoration> является визуальным декоративным элементом, который можно добавить в текст.  Имеется четыре типа оформления текста: подчеркивание, базовый план, зачеркивание и надчеркивание.  В следующем примере показано расположение элементов оформления текста относительно текста.  
  
 ![Схема расположений украшений текста](../../../../docs/framework/wpf/advanced/media/textdecoration01.png "TextDecoration01")  
Пример типов оформления текста  
  
 Чтобы добавить оформление текста в текст, создайте объект <xref:System.Windows.TextDecoration> и измените его свойства.  Использование свойства <xref:System.Windows.TextDecoration.Location%2A> позволяет указать, где размещается оформление текста, например, подчеркивание.  Использование свойства <xref:System.Windows.TextDecoration.Pen%2A> позволяет определить внешний вид оформления текста, например, сплошная заливка или градиент.  Если не указано значение свойства <xref:System.Windows.TextDecoration.Pen%2A>, оформление будет по умолчанию того же цвета, что и текст.  Определив объект <xref:System.Windows.TextDecoration>, добавьте его в коллекцию <xref:System.Windows.TextDecorations> нужного объекта текста.  
  
 В следующем примере показано оформление текста с помощью кисти линейного градиента и штрихового пера.  
  
 ![Украшение текста с подчеркиванием линейным градиентом](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
Пример подчеркивания линейной градиентной кистью и штриховым пером  
  
 Объект <xref:System.Windows.Documents.Hyperlink> является элементом содержимого нефиксированного формата встроенного уровня, позволяющим размещать гиперссылки в содержимом нефиксированного формата.  По умолчанию <xref:System.Windows.Documents.Hyperlink> использует объект <xref:System.Windows.TextDecoration> для отображения подчеркивания.  Объекты <xref:System.Windows.TextDecoration> могут уменьшить производительность при создании, особенно при большом количестве объектов <xref:System.Windows.Documents.Hyperlink>.  При частом использовании гиперссылок <xref:System.Windows.Documents.Hyperlink>, можно отображать подчеркивание только при возникновении события, например, <xref:System.Windows.ContentElement.MouseEnter>.  
  
 В следующем примере подчеркивание ссылки "Моя страница MSN" является динамическим — оно появляется только при возникновении события <xref:System.Windows.ContentElement.MouseEnter>.  
  
 ![Гиперссылки, отображающие TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Гиперссылки, определенные с помощью TextDecorations  
  
 Дополнительные сведения см. в разделе [Определение того, подчеркнута ли ссылка](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## Пример  
 В следующем примере кода для оформления текста подчеркиванием используется значение шрифта по умолчанию.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 В следующем примере кода подчеркивание текста создается с помощью сплошной цветной кисти.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 В следующем примере кода подчеркивание текста создается с помощью кисти линейного градиента для пунктирного пера.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## См. также  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [Определение того, подчеркнута ли ссылка](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)