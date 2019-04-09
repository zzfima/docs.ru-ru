---
title: Расширение разметки ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: e8a36a1b8592146eb2474805638cdc3697adb0c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172943"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="ea8ee-102">Расширение разметки ColorConvertedBitmap</span><span class="sxs-lookup"><span data-stu-id="ea8ee-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="ea8ee-103">Предоставляет способ для указания источника точечного рисунка, который не имеет внедренного профиля.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="ea8ee-104">Цвет контекста или профиля определяется [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], так как источник изображения [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea8ee-104">Color contexts / profiles are specified by [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], as is the image source [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ea8ee-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="ea8ee-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ea8ee-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="ea8ee-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="ea8ee-107">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Непрофилируемых растрового изображения.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-107">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="ea8ee-108">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Профиля конфигурации источника.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-108">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="ea8ee-109">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Назначения профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="ea8ee-109">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea8ee-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea8ee-110">Remarks</span></span>  
 <span data-ttu-id="ea8ee-111">Данного расширения разметки предназначено для заполнения связанного набора значений свойств источник изображения, такие как <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="ea8ee-112">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> `ColorConvertedBitmap` <span data-ttu-id="ea8ee-113">(или `ColorConvertedBitmapExtension`) не может использоваться в синтаксисе элемента свойства, так как значения может устанавливаться только как значения в начальном конструкторе, который является строкой следующего идентификатора расширения.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-113">(or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 `ColorConvertedBitmap` <span data-ttu-id="ea8ee-114">является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-114">is a markup extension.</span></span> <span data-ttu-id="ea8ee-115">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="ea8ee-116">Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea8ee-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="ea8ee-117">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ea8ee-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8ee-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ea8ee-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="ea8ee-119">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="ea8ee-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="ea8ee-120">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="ea8ee-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
