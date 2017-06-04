---
title: "Практическое руководство. Использование кэшированного элемента в качестве кисти | Microsoft Docs"
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
  - "BitmapCache [WPF], использование"
  - "BitmapCacheBrush [WPF], использование"
  - "кэшированный элемент [WPF], использование в качестве кисти"
  - "CacheMode [WPF], использование"
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Использование кэшированного элемента в качестве кисти
Класс <xref:System.Windows.Media.BitmapCacheBrush> предназначен для эффективного многократного использования кэшированного элемента.  Для кэширования элемента создайте новый экземпляр класса <xref:System.Windows.Media.BitmapCache> и задайте его в свойстве <xref:System.Windows.UIElement.CacheMode%2A> элемента.  
  
## Пример  
 В следующем примере кода показано многократное использование кэшированного элемента.  Кэшируемый элемент представляет собой элемент управления <xref:System.Windows.Controls.Image>, в котором выводится крупное изображение.  Элемент управления <xref:System.Windows.Controls.Image> кэшируется в виде растрового изображения с помощью класса <xref:System.Windows.Media.BitmapCache>, а многократное использование кэша реализуется путем его присваивания объекту <xref:System.Windows.Media.BitmapCacheBrush>.  Для демонстрации эффективного многократного использования кисть используется в качестве фона для двадцати пяти кнопок.  
  
 [!code-xml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## См. также  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)