---
title: Расширение разметки ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 7d14ddc6276b9dd7baee12e267e8af1250bc11ab
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582771"
---
# <a name="colorconvertedbitmap-markup-extension"></a>Расширение разметки ColorConvertedBitmap
Предоставляет способ указания источника точечного рисунка, не имеющего внедренного профиля. Цветовые контексты и профили задаются с помощью URI, как и URI источника изображения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`imageSource`|URI непрофилированного точечного рисунка.|  
|`sourceIIC`|Универсальный код ресурса (URI) конфигурации исходного профиля.|  
|`destinationIIC`|Универсальный код ресурса (URI) конфигурации конечного профиля|  
  
## <a name="remarks"></a>Заметки  
 Это расширение разметки предназначено для заполнения связанного набора значений свойств источника изображения, таких как <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. `ColorConvertedBitmap` (или `ColorConvertedBitmapExtension`) нельзя использовать в синтаксисе элемента свойства, так как значения могут быть заданы только в качестве значений в исходном конструкторе, который является строкой, следующей за идентификатором расширения.  
  
 `ColorConvertedBitmap` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Общие сведения об обработке изображений](../graphics-multimedia/imaging-overview.md)
