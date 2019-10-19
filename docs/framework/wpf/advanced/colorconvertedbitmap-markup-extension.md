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
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="2d029-102">Расширение разметки ColorConvertedBitmap</span><span class="sxs-lookup"><span data-stu-id="2d029-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="2d029-103">Предоставляет способ указания источника точечного рисунка, не имеющего внедренного профиля.</span><span class="sxs-lookup"><span data-stu-id="2d029-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="2d029-104">Цветовые контексты и профили задаются с помощью URI, как и URI источника изображения.</span><span class="sxs-lookup"><span data-stu-id="2d029-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2d029-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="2d029-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2d029-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="2d029-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="2d029-107">URI непрофилированного точечного рисунка.</span><span class="sxs-lookup"><span data-stu-id="2d029-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="2d029-108">Универсальный код ресурса (URI) конфигурации исходного профиля.</span><span class="sxs-lookup"><span data-stu-id="2d029-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="2d029-109">Универсальный код ресурса (URI) конфигурации конечного профиля</span><span class="sxs-lookup"><span data-stu-id="2d029-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d029-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2d029-110">Remarks</span></span>  
 <span data-ttu-id="2d029-111">Это расширение разметки предназначено для заполнения связанного набора значений свойств источника изображения, таких как <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d029-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="2d029-112">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="2d029-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="2d029-113">`ColorConvertedBitmap` (или `ColorConvertedBitmapExtension`) нельзя использовать в синтаксисе элемента свойства, так как значения могут быть заданы только в качестве значений в исходном конструкторе, который является строкой, следующей за идентификатором расширения.</span><span class="sxs-lookup"><span data-stu-id="2d029-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="2d029-114">`ColorConvertedBitmap` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="2d029-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="2d029-115">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="2d029-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="2d029-116">Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.</span><span class="sxs-lookup"><span data-stu-id="2d029-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="2d029-117">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="2d029-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d029-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2d029-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="2d029-119">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="2d029-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="2d029-120">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="2d029-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
