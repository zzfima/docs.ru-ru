---
title: "Практическое руководство. Использование SystemFonts | Microsoft Docs"
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
  - "шрифты, системные шрифты"
  - "системные шрифты"
  - "класс SystemFonts"
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Практическое руководство. Использование SystemFonts
В этом примере показан способ использования статических ресурсов класса<xref:System.Windows.SystemFonts> для изменения стиля или настроек кнопки.  
  
## Пример  
 Системные ресурсы предоставляют несколько значений, определяемых системой, в качестве ресурсов и свойств, помогающих создавать визуализацию, согласованную с параметрами системы.  <xref:System.Windows.SystemFonts> является классом, содержащим значения системного шрифта в виде статических свойств и свойства со ссылками на ключи ресурсов, которые можно использовать для доступа к этим значениями динамически во время выполнения.  Например, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> является значением <xref:System.Windows.SystemFonts>, а <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> является ключом соответствующего ресурса.  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно использовать члены <xref:System.Windows.SystemFonts> как статические свойства или ссылки динамического ресурса \(со статическим значением свойства в качестве ключа\).  Используйте динамическую ссылку на ресурс, если метрика шрифта должна автоматически обновляться во время выполнения приложения; в противном случае используйте ссылку на статическое значение.  
  
> [!NOTE]
>  К именам свойств, используемых в качестве ключей ресурсов, добавляется суффикс «Key».  
  
 В следующем примере демонстрируется способ получения доступа и использования свойств <xref:System.Windows.SystemFonts> как статических значений для изменения стиля или настроек кнопки.  Этот пример разметки присваивает кнопке значения <xref:System.Windows.SystemFonts>.  
  
 [!code-xml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Для того, чтобы использовать значения <xref:System.Windows.SystemFonts> в коде, необязательно использовать статическое значение или ссылку динамического ресурса.  Вместо этого можно использовать неключевые свойства класса <xref:System.Windows.SystemFonts>.  Хотя неключевые свойства очевидно определены как статические, поведение во время выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], размещенного системой, будет пересчитывать свойства в режиме реального времени и правильно учитывать управляемые пользователем изменения значений системы.  Следующий пример показывает, как задать параметры шрифта кнопки.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## См. также  
 <xref:System.Windows.SystemFonts>   
 [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Использование SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [Использование разделов системных шрифтов](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)   
 [Расширение разметки x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md)   
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)