---
title: "Как использовать SystemParameters | Microsoft Docs"
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
  - "SystemParameters - класс"
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Как использовать SystemParameters
В этом примере показывается, как получить доступ к свойствам <xref:System.Windows.SystemParameters> и использовать их, чтобы разработать или настроить кнопку.  
  
## Пример  
 Системные ресурсы предоставляют несколько параметров системы в виде ресурсов, способствующих созданию визуальных элементов с учетом параметров системы.  <xref:System.Windows.SystemParameters> представляет собой класс, содержащий как свойства значений параметров системы, так и ключи ресурсов, привязанные к этим значениям.  Например, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> является значением свойства <xref:System.Windows.SystemParameters>, а <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> является соответствующим ключом ресурса.  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно использовать члены объекта <xref:System.Windows.SystemParameters> как статическое свойство или динамические ссылки на ресурс \(со статическим значением свойства в качестве ключа\).  Используйте динамическую ссылку на ресурс, если требуется системное значение для автоматического обновления во время выполнения приложения; в противном случае, используйте статическую ссылку.  Ключи ресурсов имеют суффикс `Key`, добавленный к имени свойства.  
  
 Следующий пример показывает, как получить доступ и использовать статические значения объекта <xref:System.Windows.SystemParameters> для разработки или настройки кнопки.  Этот пример разметки изменяет размер кнопки, применяя к ней значения <xref:System.Windows.SystemParameters>.  
  
 [!code-xml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Чтобы использовать значения объекта <xref:System.Windows.SystemParameters> в коде, нет необходимости использовать статические или динамические ссылки на ресурс.  Вместо этого используйте значения класса <xref:System.Windows.SystemParameters>.  Хотя неключевые свойства, по всей видимости, определены как статические, поведение во время выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], размещенного системой, будет пересчитывать свойства в режиме реального времени и правильно учитывать управляемые пользователем изменения значений системы. В следующем примере показано, как задать ширину и высоту кнопки с помощью значений <xref:System.Windows.SystemParameters>.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## См. также  
 <xref:System.Windows.SystemParameters>   
 [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Использование SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [Использование разделов системных параметров](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)