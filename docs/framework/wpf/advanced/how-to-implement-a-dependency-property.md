---
title: "Практическое руководство. Реализация свойства зависимостей | Microsoft Docs"
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
  - "свойства зависимостей, резервирование свойств"
  - "свойства, резервирование с помощью свойств зависимостей"
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Реализация свойства зависимостей
В этом примере показано, как обеспечить поддержку свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] с использованием поля <xref:System.Windows.DependencyProperty>, определяя тем самым [свойство зависимостей](GTMT).  Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как [свойство зависимостей](GTMT).  
  
## Пример  
 В следующем примере сначала регистрируется [свойство зависимостей](GTMT) путем вызова метода <xref:System.Windows.DependencyProperty.Register%2A>.  Поле идентификатора, используемое для хранения имени и характеристик [свойства зависимостей](GTMT), должно иметь имя <xref:System.Windows.DependencyProperty.Name%2A>, которое выбирается для свойства зависимостей в составе вызова <xref:System.Windows.DependencyProperty.Register%2A> с добавлением строкового литерала `Property`.  Например, если регистрируется свойство зависимостей с именем <xref:System.Windows.DependencyProperty.Name%2A> для поля `Location`, то поле идентификатора, определяемое для свойства зависимостей, должно называться `LocationProperty`.  
  
 В этом примере для [свойства зависимостей](GTMT) и его метода доступа [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] используется имя `State`; поле идентификатора называется `StateProperty`; тип свойства — <xref:System.Boolean>; тип, регистрирующий [свойство зависимостей](GTMT) — `MyStateControl`.  
  
 Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство, и определенные аспекты приложения стиля системы свойств могут работать не так, как ожидалось.  
  
 Для [свойства зависимостей](GTMT) можно также указать используемые по умолчанию метаданные.  В этом примере в качестве значения по умолчанию для [свойства зависимостей](GTMT) `State` регистрируется значение `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Дополнительные сведения о том, как и зачем реализовать [свойство зависимостей](GTMT) в противоположность поддержке свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с использованием закрытого поля, см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## См. также  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)