---
title: '{} Escape-последовательности - расширение разметки'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: 9f6743dd8a82891ac2233978550e5679130de0be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182079"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="f3450-102">{}Escape-последовательность/расширение разметки</span><span class="sxs-lookup"><span data-stu-id="f3450-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="f3450-103">Предоставляет escape-последовательности XAML для значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f3450-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="f3450-104">Escape-последовательность позволяет последующие значения в атрибуте интерпретируется как литерал.</span><span class="sxs-lookup"><span data-stu-id="f3450-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f3450-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="f3450-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="f3450-106">Использование элемента свойства XAML</span><span class="sxs-lookup"><span data-stu-id="f3450-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f3450-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="f3450-107">XAML Values</span></span>  
  
|||  
|-|-|  
|*<span data-ttu-id="f3450-108">literalValue</span><span class="sxs-lookup"><span data-stu-id="f3450-108">literalValue</span></span>*|<span data-ttu-id="f3450-109">Буквенная строка, следующий за escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="f3450-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="f3450-110">Обычно эта строка содержит открытия или закрытия фигурной скобкой ("{" или "}").</span><span class="sxs-lookup"><span data-stu-id="f3450-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3450-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3450-111">Remarks</span></span>  
 <span data-ttu-id="f3450-112">Escape-последовательность ({}) используется, чтобы открывающую фигурную скобку ({}) может использоваться как литеральный символ в XAML.</span><span class="sxs-lookup"><span data-stu-id="f3450-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="f3450-113">Средства чтения XAML обычно используется открывающая фигурная скобка ({}) для обозначения точки входа расширение разметки; тем не менее, они сначала проверьте следующий символ, чтобы определить, является ли закрывающей фигурной скобкой (}).</span><span class="sxs-lookup"><span data-stu-id="f3450-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="f3450-114">Только когда две фигурные скобки ({}) являются смежными, поддерживают, они считаются escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f3450-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="f3450-115">При обнаружении escape-последовательность, средство чтения XAML должно обрабатывать оставшейся части строки как строка.</span><span class="sxs-lookup"><span data-stu-id="f3450-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="f3450-116">Тем не менее если escape-последовательность применяется к члену, который имеет преобразователь типов, строка может претерпеть преобразование типов, когда он интерпретируется средством записи XAML.</span><span class="sxs-lookup"><span data-stu-id="f3450-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="f3450-117">Escape-последовательность не является расширением разметки и не поддерживается классом.</span><span class="sxs-lookup"><span data-stu-id="f3450-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="f3450-118">Тем не менее он является условным обозначением, должны учитывать средства чтения XAML (включая пользовательские средства чтения XAML).</span><span class="sxs-lookup"><span data-stu-id="f3450-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="f3450-119">Знак кавычек ("") не может использоваться как escape-последовательность, таким образом.</span><span class="sxs-lookup"><span data-stu-id="f3450-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="f3450-120">Если вам нужно установить знак кавычек в качестве значения свойства для свойства, не являющегося содержимым, используйте синтаксис элемента свойства и поместите знак кавычки в виде строки внутри элемента свойства или использовать сущности символов XML.</span><span class="sxs-lookup"><span data-stu-id="f3450-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="f3450-121">Для свойства содержимого знак кавычки может быть всего содержимого.</span><span class="sxs-lookup"><span data-stu-id="f3450-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="f3450-122">Escape-последовательность ({}) — часто требуется при указании типа XML, который должен включать квалификатор пространства имен в месте, где может отображаться расширение разметки XAML.</span><span class="sxs-lookup"><span data-stu-id="f3450-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="f3450-123">Сюда входят начала значение атрибута XAML и в расширении разметки, сразу после знака равенства (=).</span><span class="sxs-lookup"><span data-stu-id="f3450-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="f3450-124">В следующем примере показано escape-последовательности для пространства имен XML, отображаемый в начале значение атрибута XAML.</span><span class="sxs-lookup"><span data-stu-id="f3450-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="f3450-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f3450-125">See also</span></span>

- [<span data-ttu-id="f3450-126">Преобразователи типов или расширения разметки для XAML</span><span class="sxs-lookup"><span data-stu-id="f3450-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="f3450-127">Сущности знаков XML и XAML</span><span class="sxs-lookup"><span data-stu-id="f3450-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)
