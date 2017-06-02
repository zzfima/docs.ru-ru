---
title: "Практическое руководство. Регистрация вложенного свойства зависимостей | Microsoft Docs"
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
  - "вложенные свойства, регистрация"
  - "регистрация присоединенных свойств"
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Регистрация вложенного свойства зависимостей
В этом примере демонстрируется регистрация [вложенного свойства зависимостей](GTMT) и предоставление общих методов доступа для использования свойства в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и в коде.  Вложенные свойства зависимостей являются понятиями синтаксиса, определенными в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Большинство вложенных свойств для типов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также реализовано как [свойства зависимостей](GTMT).  [Свойства зависимостей](GTMT) можно использовать для любых типов <xref:System.Windows.DependencyObject>.  
  
## Пример  
 В следующем примере показано, как зарегистрировать вложенное свойство в качестве свойства зависимости с помощью метода <xref:System.Windows.DependencyProperty.RegisterAttached%2A>.  Класс поставщика имеет возможность предоставления метаданных по умолчанию для свойства, применяемого в случаях, когда свойство используется в другом классе, а этот класс не переопределяет метаданные.  В этом примере значение по умолчанию свойства `IsBubbleSource` равно `false`.  
  
 Класс поставщика для присоединенного свойства \(даже если оно не зарегистрировано как свойство зависимостей\) должен предоставлять статические методы доступа get и set, соответствующие правилам именования `Set`*\[имя\_присоединенного\_свойства\]* и `Get`*\[имя\_присоединенного\_свойства\]*. Эти методы доступа требуются для того, чтобы действующее средство чтения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознало свойство как атрибут в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и разрешило соответствующие типы.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## См. также  
 <xref:System.Windows.DependencyProperty>   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)