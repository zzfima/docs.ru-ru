---
title: "Как обработать загруженное событие | Microsoft Docs"
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
  - "события, Загруженные"
  - "загружаемые события"
  - "XAML, загружаемые события"
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Как обработать загруженное событие
В этом примере показан порядок обработки события <xref:System.Windows.FrameworkElement.Loaded?displayProperty=fullName> и соответствующий скрипт для обработки этого события.  Обработчик создает объект <xref:System.Windows.Controls.Button> при загрузке страницы.  
  
## Пример  
 В следующем примере используется [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] вместе с файлом кода программной части.  
  
 [!code-xml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## См. также  
 <xref:System.Windows.FrameworkElement>   
 [События времени жизни объекта](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)