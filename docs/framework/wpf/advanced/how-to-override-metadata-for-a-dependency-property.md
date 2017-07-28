---
title: "Практическое руководство. Переопределение метаданных для свойств зависимости | Microsoft Docs"
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
  - "свойства зависимостей, переопределение метаданных"
  - "метаданные, переопределение для свойств зависимостей"
  - "свойства зависимостей - переопределение"
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Переопределение метаданных для свойств зависимости
В этом примере демонстрируется переопределение метаданных свойства зависимости по умолчанию зависимости, взятых из наследованного класса, с помощью вызова метода <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> и предоставления метаданных определенного типа.  
  
## Пример  
 Путем определения <xref:System.Windows.PropertyMetadata> класс может определить поведение [свойства зависимости](GTMT), например, обратные вызовы значения по умолчанию и системы свойств.  Многие классы свойства зависимости уже имеют метаданные по умолчанию, установленные как часть процесса их регистрации.  Это включает свойства зависимости, которые являются частью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].  Класс, который наследует свойство зависимости через наследование, может переопределить исходные метаданные, так что характеристики свойства, которые могут изменяться через метаданные, будут соответствовать любым особым требованиям подкласса.  
  
 Переопределение метаданных в свойстве зависимости должно быть выполнена для этого свойства, используемого системой свойств \(это соответствует случаю, когда создаются определенные экземпляры объектов, регистрирующие свойство\).  Вызов <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> должен быть выполнен в статическом конструкторе типа, предоставляющего себя в качестве параметра `forType` для <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.  При попытке изменить созданные метаданные существующего типа\-владельца не возникнет исключения, но это приведет к несогласованному поведению в системе свойства.  Кроме того, метаданные могут переопределяться один раз для каждого типа.  Последующие попытки перезаписать метаданные для того же типа вызовут исключение.  
  
 В следующем примере пользовательский класс `MyAdvancedStateControl` переопределяет метаданные для `StateProperty` с помощью `MyAdvancedStateControl` с новыми метаданными свойства.  Например, значение `StateProperty` по умолчанию является теперь `true`, если свойству поступает запрос на создание нового экземпляра `MyAdvancedStateControl`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## См. также  
 <xref:System.Windows.DependencyProperty>   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)