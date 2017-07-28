---
title: "Практическое руководство. Определение и создание ссылки на ресурс | Microsoft Docs"
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
  - "определение ресурсов"
  - "создание ссылок на ресурсы"
  - "ресурсы, определение"
  - "ресурсы, создание ссылок"
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Определение и создание ссылки на ресурс
В этом примере описывается порядок определения ресурса и создания ссылки на него с помощью атрибута в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## Пример  
 В следующем примере определяются ресурсы двух типов: ресурс <xref:System.Windows.Media.SolidColorBrush>, а также несколько ресурсов <xref:System.Windows.Style>.  Ресурс <xref:System.Windows.Media.SolidColorBrush>`MyBrush` используется для предоставления значений нескольких свойств, каждое из которых принимает значение типа <xref:System.Windows.Media.Brush>.  Каждый из ресурсов класса <xref:System.Windows.Style> \(`PageBackground`, `TitleText` и `Label`\) предназначен для определенного типа элемента управления.  Стили используются для установки нескольких свойств для целевых элементов управления. Для этого создается ссылка ключа ресурса на ресурс стиля, который используется для установки свойства <xref:System.Windows.FrameworkElement.Style%2A> для нескольких конкретных элементов управления, определенных в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Обратите внимание, что одно из свойств метода установки стиля `Label` также ссылается на ресурс `MyBrush`, определенный ранее.  Это стандартный способ. Однако следует учитывать, что анализ ресурсов и их добавление в словарь ресурсов осуществляется в том порядке, в котором они заданы.  Если для ссылки на ресурсы из другого ресурса используется [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md), их запрос также осуществляется в том порядке, в котором они найдены в словаре.  Убедитесь, что любые ресурсы, на которые можно ссылаться, определены в коллекции ресурсов до их запроса.  При необходимости можно обойти строгий порядок создания ссылок ресурсов. Для этого следует использовать [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) для ссылки на ресурс во время выполнения. Однако следует учитывать, что использование этого способа DynamicResource может привести к снижению производительности.  Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)