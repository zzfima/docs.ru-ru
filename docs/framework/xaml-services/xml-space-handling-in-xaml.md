---
title: Обработка xml:space в языке XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458795"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="b9945-102">Обработка xml:space в языке XAML</span><span class="sxs-lookup"><span data-stu-id="b9945-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="b9945-103">Атрибут `xml:space` представляет собой XML-определенный атрибут, объявляющий значимое поведение обработки пробелов в элементе Object.</span><span class="sxs-lookup"><span data-stu-id="b9945-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="b9945-104">Это поведение относится ко всему содержимому (внутреннему тексту), содержащемуся в элементе, где `xml:space` объявлен, а также области для дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="b9945-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b9945-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="b9945-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="b9945-106">\- или -</span><span class="sxs-lookup"><span data-stu-id="b9945-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="b9945-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b9945-107">Remarks</span></span>  
 <span data-ttu-id="b9945-108">Определение атрибута `xml:space` в XAML, включая два возможных значения, является производным от `xml:space`, как определено спецификацией W3C для XML в качестве "специального атрибута".</span><span class="sxs-lookup"><span data-stu-id="b9945-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="b9945-109">Значением по умолчанию для атрибута `xml:space` является литеральное значение `"default"`.</span><span class="sxs-lookup"><span data-stu-id="b9945-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="b9945-110">Для значения `"default"`или если `xml:space` не указано вообще, поведением анализа значимого пробела является обработка по умолчанию, как определено в разделе [Обработка пробелов в XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="b9945-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="b9945-111">Чтобы сохранить пробелы в содержимом объектного элемента, укажите `xml:space="preserve"` для этого элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="b9945-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="b9945-112">При большинстве интерпретаций `xml:space` атрибуты, а значение атрибута ограничивается дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="b9945-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="b9945-113">Полное описание обработки пробелов в XAML см. [в разделе Обработка пробелов в XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="b9945-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9945-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b9945-114">See also</span></span>

- [<span data-ttu-id="b9945-115">Обработка пробелов в XAML</span><span class="sxs-lookup"><span data-stu-id="b9945-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="b9945-116">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="b9945-116">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
