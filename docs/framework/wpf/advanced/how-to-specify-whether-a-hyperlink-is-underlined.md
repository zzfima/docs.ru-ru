---
title: "Практическое руководство. Определение того, подчеркнута ли ссылка | Microsoft Docs"
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
  - "классы, TextDecoration"
  - "Hyperlink - тип элемента управления"
  - "TextDecoration - класс"
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Определение того, подчеркнута ли ссылка
Объект <xref:System.Windows.Documents.Hyperlink> является элементом содержимого нефиксированного формата встроенного уровня, позволяющим размещать гиперссылки в содержимом нефиксированного формата.  По умолчанию <xref:System.Windows.Documents.Hyperlink> использует объект <xref:System.Windows.TextDecoration> для отображения подчеркивания.  Объекты <xref:System.Windows.TextDecoration> могут уменьшить производительность при создании, особенно при большом количестве объектов <xref:System.Windows.Documents.Hyperlink>.  При частом использовании гиперссылок <xref:System.Windows.Documents.Hyperlink>, можно отображать подчеркивание только при возникновении события, например, <xref:System.Windows.ContentElement.MouseEnter>.  
  
 В следующем примере подчеркивание ссылки "Моя страница MSN" является динамическим — оно появляется только при возникновении события <xref:System.Windows.ContentElement.MouseEnter>.  
  
 ![Гиперссылки, отображающие TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Гиперссылки, определенные с помощью TextDecorations  
  
## Пример  
 В следующем примере разметки демонстрируется элемент <xref:System.Windows.Documents.Hyperlink>, определенный с подчеркиванием и без него:  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 В следующем примере кода демонстрируется создание подчеркивания для <xref:System.Windows.Documents.Hyperlink> при событии <xref:System.Windows.ContentElement.MouseEnter> и удалите его при событии <xref:System.Windows.ContentElement.MouseLeave>.  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## См. также  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Создание оформления текста](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)