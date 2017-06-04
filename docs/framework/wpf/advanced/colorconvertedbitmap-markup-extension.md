---
title: "Расширение разметки ColorConvertedBitmap | Microsoft Docs"
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
  - "ColorConvertedBitmap - расширение разметки"
  - "XAML, ColorConvertedBitmap - расширение разметки"
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Расширение разметки ColorConvertedBitmap
Предоставляет способ указания источника точечного рисунка без внедренного профиля.  Цвет контекста или профиля определяется [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], а исходное изображение — [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## Использование атрибута XAML  
  
```  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`imageSource`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] точечного рисунка без профиля.|  
|`sourceIIC`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] исходной конфигурации профиля.|  
|`destinationIIC`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] конечной конфигурации профиля|  
  
## Заметки  
 Это расширение разметки предназначено для заполнения связанного набора значений свойств источника изображения, например <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 Синтаксис атрибута является наиболее распространенным синтаксисом, который используется с этим расширением разметки.  `ColorConvertedBitmap` \(или `ColorConvertedBitmapExtension`\) не может использоваться в синтаксисе элементов свойства, поскольку значения могут быть установлены только в начальном конструкторе, который является строкой следующего идентификатора расширения.  
  
 `ColorConvertedBitmap` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы { and } в синтаксисе их атрибутов, который является соглашением, по которому процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)