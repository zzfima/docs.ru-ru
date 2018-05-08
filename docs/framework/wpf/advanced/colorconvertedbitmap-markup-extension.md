---
title: Расширение разметки ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 9b39e30cbe4e0bedc88c859f013b4d7175f7eb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="colorconvertedbitmap-markup-extension"></a>Расширение разметки ColorConvertedBitmap
Предоставляет способ для указания источника точечного рисунка, у которого нет встроенным профилем. Цвет контекста или профиля определяется [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], как исходное изображение [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`imageSource`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Nonprofiled растрового изображения.|  
|`sourceIIC`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Профиля конфигурации источника.|  
|`destinationIIC`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Назначения профиля конфигурации|  
  
## <a name="remarks"></a>Примечания  
 Это расширение разметки предназначено для заполнения связанного набора значений свойств источник изображения, такие как <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. `ColorConvertedBitmap` (или `ColorConvertedBitmapExtension`) не может использоваться в синтаксис элемента свойства, поскольку значения может устанавливаться только как значения в начальном конструкторе, который является строкой следующего идентификатора расширения.  
  
 `ColorConvertedBitmap` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>  
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
