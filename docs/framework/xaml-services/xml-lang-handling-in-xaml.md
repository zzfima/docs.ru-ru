---
title: Обработка xml:lang в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b3f236b2378d6af78f034856e3ba0f7a9e17993c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837146"
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="d1df9-102">Обработка xml:lang в XAML</span><span class="sxs-lookup"><span data-stu-id="d1df9-102">xml:lang Handling in XAML</span></span>
<span data-ttu-id="d1df9-103">Атрибут `xml:lang` является XML-атрибутом, который объявляет сведения о языке и региональных параметрах для элемента в XML.</span><span class="sxs-lookup"><span data-stu-id="d1df9-103">The `xml:lang` attribute is an XML-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="d1df9-104">Такое же значение атрибута сохраняется в XAML; однако действуют некоторые дополнительные факторы.</span><span class="sxs-lookup"><span data-stu-id="d1df9-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d1df9-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="d1df9-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:lang="rfc3066lang" />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d1df9-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="d1df9-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1df9-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="d1df9-107">*rfc3066lang*</span></span>|<span data-ttu-id="d1df9-108">Строка, которая является производной от стандарта [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) и определяет язык или язык-регион.</span><span class="sxs-lookup"><span data-stu-id="d1df9-108">A string that is derived from the [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="d1df9-109">В последнем варианте язык и регион разделяются дефисом.</span><span class="sxs-lookup"><span data-stu-id="d1df9-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="d1df9-110">Дополнительные сведения о значениях и формате см. в разделе <xref:System.Windows.Markup.XmlLanguage> .</span><span class="sxs-lookup"><span data-stu-id="d1df9-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1df9-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="d1df9-111">Remarks</span></span>  
 <span data-ttu-id="d1df9-112">Определение атрибута `xml:lang` в [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] является производным от `xml:lang`, как определено с помощью консорциум W3C (W3C) for XML.</span><span class="sxs-lookup"><span data-stu-id="d1df9-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for XML.</span></span> <span data-ttu-id="d1df9-113">Сведения о языке и региональных параметрах потенциально обрабатываются элементами по-разному, в зависимости от реализации этих элементов; однако обработка [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] атрибута `xml:lang` по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1df9-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>  
  
 <span data-ttu-id="d1df9-114">Значение по умолчанию атрибута `xml:lang` представляет собой пустую строку на уровне атрибута.</span><span class="sxs-lookup"><span data-stu-id="d1df9-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>  
  
 <span data-ttu-id="d1df9-115">Действие атрибута `xml:lang` и значение этого атрибута обычно сохраняются в дочерних элементах при интерпретации системами, которые работают со значениями `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="d1df9-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>  
  
 <span data-ttu-id="d1df9-116">При интерпретации модулем записи XAML служб XAML .NET Framework значение `xml:lang` может создать объекты <xref:System.Windows.Markup.XmlLanguage> или <xref:System.Globalization.CultureInfo> в базовом объектном представлении; однако это поведение зависит от того, является ли значение, указанное для `xml:lang` , допустимой конструкцией для этих классов.</span><span class="sxs-lookup"><span data-stu-id="d1df9-116">When interpreted by XAML writers of .NET Framework XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>  
  
 <span data-ttu-id="d1df9-117">Инфраструктуры могут создавать связи между определенными инфраструктурой свойствами и значением `xml:lang` в XML, применяя <xref:System.Windows.Markup.XmlLangPropertyAttribute> к свойству.</span><span class="sxs-lookup"><span data-stu-id="d1df9-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>  
  
## <a name="wpf-usage-nodes"></a><span data-ttu-id="d1df9-118">Узлы использования WPF</span><span class="sxs-lookup"><span data-stu-id="d1df9-118">WPF Usage Nodes</span></span>  
 <span data-ttu-id="d1df9-119">Для элементов, которые являются производными классами от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, можно использовать эквивалентное свойство зависимостей <xref:System.Windows.FrameworkElement.Language%2A> вместо атрибута `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="d1df9-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="d1df9-120">По умолчанию свойство <xref:System.Windows.FrameworkElement.Language%2A> использует "en-US", если не установлено иное, посредством этого свойства или путем обработки атрибута `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="d1df9-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1df9-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1df9-121">See also</span></span>

- [<span data-ttu-id="d1df9-122">Глобализация для WPF</span><span class="sxs-lookup"><span data-stu-id="d1df9-122">Globalization for WPF</span></span>](../wpf/advanced/globalization-for-wpf.md)
