---
title: Обработка xml:lang в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 508c1151b1b196a84b7c3a576e18d10c0a706fad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692406"
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="feec0-102">Обработка xml:lang в XAML</span><span class="sxs-lookup"><span data-stu-id="feec0-102">xml:lang Handling in XAML</span></span>
<span data-ttu-id="feec0-103">Атрибут `xml:lang` — это определенный [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]атрибут, который объявляет язык и региональные параметры для элемента в XML.</span><span class="sxs-lookup"><span data-stu-id="feec0-103">The `xml:lang` attribute is an [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="feec0-104">Такое же значение атрибута сохраняется в XAML; однако действуют некоторые дополнительные факторы.</span><span class="sxs-lookup"><span data-stu-id="feec0-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="feec0-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="feec0-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:lang="rfc3066lang" />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="feec0-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="feec0-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="feec0-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="feec0-107">*rfc3066lang*</span></span>|<span data-ttu-id="feec0-108">Строка, которая является производной от стандарта [RFC 3066](https://go.microsoft.com/fwlink/?LinkId=132454) и определяет язык или язык-регион.</span><span class="sxs-lookup"><span data-stu-id="feec0-108">A string that is derived from the [RFC 3066](https://go.microsoft.com/fwlink/?LinkId=132454) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="feec0-109">В последнем варианте язык и регион разделяются дефисом.</span><span class="sxs-lookup"><span data-stu-id="feec0-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="feec0-110">Дополнительные сведения о значениях и формате см. в разделе <xref:System.Windows.Markup.XmlLanguage> .</span><span class="sxs-lookup"><span data-stu-id="feec0-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feec0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="feec0-111">Remarks</span></span>  
 <span data-ttu-id="feec0-112">Определение атрибута `xml:lang` в [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] является производным от `xml:lang` , определенного в [!INCLUDE[TLA#tla_w3c](../../../includes/tlasharptla-w3c-md.md)] как "специальный атрибут" для [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="feec0-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the [!INCLUDE[TLA#tla_w3c](../../../includes/tlasharptla-w3c-md.md)] for [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)].</span></span> <span data-ttu-id="feec0-113">Сведения о языке и региональных параметрах потенциально обрабатываются элементами по-разному, в зависимости от реализации этих элементов; однако обработка [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] атрибута `xml:lang` по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="feec0-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>  
  
 <span data-ttu-id="feec0-114">Значение по умолчанию атрибута `xml:lang` представляет собой пустую строку на уровне атрибута.</span><span class="sxs-lookup"><span data-stu-id="feec0-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>  
  
 <span data-ttu-id="feec0-115">Действие атрибута `xml:lang` и значение этого атрибута обычно сохраняются в дочерних элементах при интерпретации системами, которые работают со значениями `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="feec0-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>  
  
 <span data-ttu-id="feec0-116">При интерпретации модулем записи XAML служб XAML .NET Framework значение `xml:lang` может создать объекты <xref:System.Windows.Markup.XmlLanguage> или <xref:System.Globalization.CultureInfo> в базовом объектном представлении; однако это поведение зависит от того, является ли значение, указанное для `xml:lang` , допустимой конструкцией для этих классов.</span><span class="sxs-lookup"><span data-stu-id="feec0-116">When interpreted by XAML writers of .NET Framework XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>  
  
 <span data-ttu-id="feec0-117">Инфраструктуры могут создавать связи между определенными инфраструктурой свойствами и значением `xml:lang` в XML, применяя <xref:System.Windows.Markup.XmlLangPropertyAttribute> к свойству.</span><span class="sxs-lookup"><span data-stu-id="feec0-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>  
  
## <a name="wpf-usage-nodes"></a><span data-ttu-id="feec0-118">Узлы использования WPF</span><span class="sxs-lookup"><span data-stu-id="feec0-118">WPF Usage Nodes</span></span>  
 <span data-ttu-id="feec0-119">Для элементов, которые являются производными классами от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, можно использовать эквивалентное свойство зависимостей <xref:System.Windows.FrameworkElement.Language%2A> вместо атрибута `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="feec0-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="feec0-120">По умолчанию свойство <xref:System.Windows.FrameworkElement.Language%2A> использует "en-US", если не установлено иное, посредством этого свойства или путем обработки атрибута `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="feec0-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feec0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="feec0-121">See also</span></span>
- [<span data-ttu-id="feec0-122">Глобализация для WPF</span><span class="sxs-lookup"><span data-stu-id="feec0-122">Globalization for WPF</span></span>](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
