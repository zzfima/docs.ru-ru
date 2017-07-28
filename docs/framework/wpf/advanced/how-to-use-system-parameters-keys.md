---
title: "Практическое руководство. Использование разделов системных параметров | Microsoft Docs"
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
  - "классы, SystemParameters"
  - "ключи ресурса, SystemParameters - класс"
  - "SystemParameters - класс"
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Использование разделов системных параметров
Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуализацию, совместимую с параметрами системы.  <xref:System.Windows.SystemParameters> является классом, который содержит значения системных параметров и ключи ресурсов, которые привязаны к значениям, например <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> и <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.  Метрики параметров системы могут использоваться в качестве статических или динамических ресурсов.  Используйте динамический ресурс, если требуется метрика параметра для автоматического обновления во время выполнения приложения; в других случаях используйте статический ресурс.  
  
> [!NOTE]
>  Динамические ресурсы имеют ключевое слово *Key*, добавляемое к имени свойства.  
  
 В следующем примере показано, как получить доступ и использовать динамические ресурсы параметров системы для стилизации или настройки кнопки.  Этот пример [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] задает размеры кнопки, присваивая параметрам <xref:System.Windows.SystemParameters> значения ширины и высоты кнопки.  
  
## Пример  
 [!code-xml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## См. также  
 [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Использование SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [Использование SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)