---
title: "Практическое руководство. Использование ResourceDictionary для управления локализуемыми строковыми ресурсами | Microsoft Docs"
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
  - "локализация [WPF], упаковка строковых ресурсов"
  - "упаковка строковых ресурсов"
  - "ResourceDictionary [WPF]"
  - "ресурсы [WPF], упаковка строковых ресурсов"
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Использование ResourceDictionary для управления локализуемыми строковыми ресурсами
В этом примере показано применение <xref:System.Windows.ResourceDictionary> для создания пакетов локализуемых строковых ресурсов для приложений [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
### Чтобы использовать ResourceDictionary для управления локализуемыми строковыми ресурсами  
  
1.  Создайте <xref:System.Windows.ResourceDictionary>, содержащий строки, которые требуется локализовать.  В следующем коде приведен пример.  
  
     [!code-xml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     В этом коде определяется строковый ресурс \(`localizedMessage`\) типа <xref:System.String> из пространства имен <xref:System> в mscorlib.dll.  
  
2.  Добавьте <xref:System.Windows.ResourceDictionary> в приложение с помощью следующего кода.  
  
     [!code-xml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Используйте строковый ресурс из разметки, используя [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] следующим образом.  
  
     [!code-xml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Используйте строковый ресурс из файла кода программной части, используя код следующим образом.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Локализуйте приложение.  Дополнительные сведения см. в разделе [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).