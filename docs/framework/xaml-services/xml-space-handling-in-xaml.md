---
title: "Обработка xml:space в языке XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a5048cbad1d2ea914d041ac3c87a43223b208c3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="8fccc-102">Обработка xml:space в языке XAML</span><span class="sxs-lookup"><span data-stu-id="8fccc-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="8fccc-103">`xml:space` Атрибут является атрибутом, определенные в XML, который объявляет поведение обработки значимых пробелов внутри элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="8fccc-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="8fccc-104">Такое поведение применимо для всего содержимого (внутренний текст), содержащихся в элементе где `xml:space` объявляется, а также фокусирует на дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="8fccc-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="8fccc-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="8fccc-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="8fccc-106">\- или -</span><span class="sxs-lookup"><span data-stu-id="8fccc-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="8fccc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fccc-107">Remarks</span></span>  
 <span data-ttu-id="8fccc-108">Определение `xml:space` атрибут в XAML, включая два возможных значения является производным от `xml:space` как определен как «специальный атрибут» по спецификации W3C для XML.</span><span class="sxs-lookup"><span data-stu-id="8fccc-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="8fccc-109">Значение по умолчанию `xml:space` атрибут-значение литерала `"default"`.</span><span class="sxs-lookup"><span data-stu-id="8fccc-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="8fccc-110">Для значения `"default"`, или если `xml:space` не отражается на всех поведение значимых пробелов синтаксического анализа не обработку по умолчанию, как определено в разделе [Обработка пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="8fccc-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="8fccc-111">Чтобы сохранить пробелы в содержимом элемента объекта, укажите `xml:space="preserve"` для этого элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="8fccc-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="8fccc-112">В большинстве интерпретаций `xml:space` действие атрибута и значение атрибута распространяются на дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="8fccc-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="8fccc-113">Полное описание обработки пробелов в XAML см. в разделе [Обработка пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="8fccc-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fccc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8fccc-114">See Also</span></span>  
 [<span data-ttu-id="8fccc-115">Обработка пробелов в XAML</span><span class="sxs-lookup"><span data-stu-id="8fccc-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="8fccc-116">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="8fccc-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
