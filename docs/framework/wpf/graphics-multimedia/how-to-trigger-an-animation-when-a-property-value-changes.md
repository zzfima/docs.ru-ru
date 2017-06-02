---
title: "Практическое руководство. Запуск анимации при изменении значения свойства | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, запуск при изменении значений свойства"
  - "Раскадровки, запуск при изменении значений свойства"
  - "использование триггера в анимации"
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Запуск анимации при изменении значения свойства
В этом примере показано использование <xref:System.Windows.Trigger> для запуска <xref:System.Windows.Media.Animation.Storyboard> при изменении значения свойства.  Можно использовать <xref:System.Windows.Trigger> внутри <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> или <xref:System.Windows.DataTemplate>.  
  
## Пример  
 В следующем примере <xref:System.Windows.Trigger> используется для анимации <xref:System.Windows.UIElement.Opacity%2A> элемента <xref:System.Windows.Controls.Button>, когда его свойство <xref:System.Windows.UIElement.IsMouseOver%2A> становится равным `true`.  
  
 [!code-xml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Запуск анимации с помощью свойства объектов <xref:System.Windows.Trigger> выполняется сложнее, чем анимация <xref:System.Windows.EventTrigger>, или анимация с помощью методов <xref:System.Windows.Media.Animation.Storyboard>.  Она «перекликается» с анимацией, определенной другими объектами <xref:System.Windows.Trigger>, но состоит из <xref:System.Windows.EventTrigger> и анимации, запускаемой методами.  
  
## См. также  
 <xref:System.Windows.Trigger>   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)