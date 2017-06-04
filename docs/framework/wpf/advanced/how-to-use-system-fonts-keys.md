---
title: "Как использовать разделы системных шрифтов | Microsoft Docs"
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
  - "классы, SystemFonts"
  - "ключи ресурса, класс SystemFonts"
  - "класс SystemFonts"
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Как использовать разделы системных шрифтов
Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуализацию, совместимую с параметрами системы.  <xref:System.Windows.SystemFonts> является классом, который содержит значения системных шрифтов и ресурсы системных шрифтов, которые привязаны к значениям, например <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Метрики системных шрифтов могут использоваться в качестве статического или динамического ресурса.  Используйте динамический ресурс, если требуется метрика шрифта для автоматического обновления во время выполнения приложения; в противном случае, используйте статический ресурс.  
  
> [!NOTE]
>  Динамические ресурсы имеют ключевое слово *Key*, добавляемое к имени свойства.  
  
 В следующем примере показано, как получить доступ к ресурсам динамических системных шрифтов и использовать их для создания стиля или настройки кнопки.  В этом примере [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] создается стиль кнопки, который присваивает ей значения <xref:System.Windows.SystemFonts>.  
  
## Пример  
 [!code-xml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## См. также  
 [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Использование SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [Использование SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)