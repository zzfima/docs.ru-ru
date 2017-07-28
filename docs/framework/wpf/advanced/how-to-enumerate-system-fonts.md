---
title: "Инструкция по перечислению системных шрифтов | Microsoft Docs"
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
  - "перечисление, системные шрифты"
  - "шрифты, перечисление"
  - "системные шрифты, перечисление"
  - "оформление, Перечисление шрифтов"
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Инструкция по перечислению системных шрифтов
## Пример  
 В следующем примере показано перечисление шрифтов в коллекции системных шрифтов.  Имя семейства шрифтов каждого <xref:System.Windows.Media.FontFamily> внутри <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> добавляется как элемент в поле со списком.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Если несколько версий одного и того же семейства шрифтов находятся в одном каталоге, перечисление шрифтов [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] возвращает самую последнюю версию шрифта.  Если сведения о версии не предоставляют разрешения, то возвращается шрифт с последней временной меткой.  Если данные о временной метке одинаковы, возвращается файл шрифта, указанный первым в алфавитном порядке.