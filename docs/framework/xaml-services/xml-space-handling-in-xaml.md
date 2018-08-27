---
title: Обработка xml:space в языке XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 051cb6b3a314509e9593ee570fd659098670e88b
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925861"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="11147-102">Обработка xml:space в языке XAML</span><span class="sxs-lookup"><span data-stu-id="11147-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="11147-103">`xml:space` Атрибут является атрибутом, определенные в XML, который объявляет поведение обработки значительных пробелов внутри элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="11147-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="11147-104">Это поведение относится к все содержимое (внутренний текст), содержащихся в элементе где `xml:space` объявляется, а также позволяет сфокусироваться на дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="11147-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="11147-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="11147-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="11147-106">\- или -</span><span class="sxs-lookup"><span data-stu-id="11147-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="11147-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="11147-107">Remarks</span></span>  
 <span data-ttu-id="11147-108">Определение `xml:space` атрибут в XAML, включая два возможных значения является производным от `xml:space` как определен как «специальный атрибут» по спецификации W3C для XML.</span><span class="sxs-lookup"><span data-stu-id="11147-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="11147-109">Значение по умолчанию `xml:space` атрибут-значение литерала `"default"`.</span><span class="sxs-lookup"><span data-stu-id="11147-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="11147-110">Для значения `"default"`, или если `xml:space` не указывается, по значительных пробелов синтаксического анализа выполняется обработка по умолчанию, как определено в разделе [-обработки пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="11147-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="11147-111">Чтобы сохранить пробел в содержимом элемента объекта, укажите `xml:space="preserve"` данного объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="11147-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="11147-112">В большинстве интерпретаций `xml:space` действие атрибута и значение атрибута относятся к дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="11147-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="11147-113">Подробное обсуждение обработки пробелов в XAML, см. в разделе [-обработки пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="11147-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11147-114">См. также</span><span class="sxs-lookup"><span data-stu-id="11147-114">See Also</span></span>  
 [<span data-ttu-id="11147-115">Обработки пробелов в XAML</span><span class="sxs-lookup"><span data-stu-id="11147-115">White-space processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="11147-116">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="11147-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
