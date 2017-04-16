---
title: "Практическое руководство. Добавление типа владельца для свойства зависимости | Microsoft Docs"
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
  - "классы, добавление в качестве владельцев свойств зависимостей"
  - "свойства зависимостей, добавление классов в качестве владельцев"
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Добавление типа владельца для свойства зависимости
В этом примере демонстрируется способ добавления класса в качестве владельца свойства зависимостей, зарегистрированного для другого типа.  Выполняя это, средство чтения данных[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и система свойств способны распознать класс в качестве дополнительного владельца свойства.  Добавление в качестве владельца при необходимости позволяет добавлять класс для предоставления метаданных определенного типа.  
  
 В следующем примере `StateProperty` является свойством, зарегистрированным классом `MyStateControl`.  Класс `UnrelatedStateControl` добавляет себя в качестве владельца `StateProperty` с помощью метода <xref:System.Windows.DependencyProperty.AddOwner%2A>, специальным образом использующего подпись, доступную для новых метаданных свойства зависимостей, так как она существует в добавленном типе.  Обратите внимание, что следует предоставить методы доступа [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] для свойства, как показано в примере [Реализация свойства зависимостей](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md), а также повторно предоставить идентификатор свойства зависимостей для класса, добавляемого в качестве владельца.  
  
 Без оболочки свойство зависимости будет по\-прежнему работать с точки зрения программного доступа с помощью <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>.  Однако, чаще всего требуется параллельное поведение системы свойств и оболочек свойств [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Оболочки облегчают программную установку свойства зависимости и обеспечивают установку свойств в качестве атрибутов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Сведения о том, как переопределить метаданные по умолчанию, содержатся в разделе [Переопределение метаданных для свойств зависимостей](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## Пример  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## См. также  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)