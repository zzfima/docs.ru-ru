---
title: '{}Escape-последовательность — расширение разметки'
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
ms.openlocfilehash: b0646c62a1342eb160d1967e86ac286429013f3c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053866"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="e5ddb-102">{}Escape-последовательность/расширение разметки</span><span class="sxs-lookup"><span data-stu-id="e5ddb-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="e5ddb-103">Предоставляет escape-последовательность XAML для значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="e5ddb-104">Escape-последовательность позволяет интерпретировать последующие значения в атрибуте как литерал.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="e5ddb-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="e5ddb-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="e5ddb-106">Использование элемента свойства XAML</span><span class="sxs-lookup"><span data-stu-id="e5ddb-106">XAML Property Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e5ddb-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="e5ddb-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5ddb-108">*литералвалуе*</span><span class="sxs-lookup"><span data-stu-id="e5ddb-108">*literalValue*</span></span>|<span data-ttu-id="e5ddb-109">Строка литерала, следующая за escape-последовательностью.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="e5ddb-110">Обычно эта строка содержит открывающую или закрывающую фигурную скобку ({или}).</span><span class="sxs-lookup"><span data-stu-id="e5ddb-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5ddb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5ddb-111">Remarks</span></span>  
 <span data-ttu-id="e5ddb-112">Escape-последовательность ({}) используется, чтобы открывающую фигурную скобку ({) можно было использовать в качестве литерального символа в XAML.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="e5ddb-113">Средства чтения XAML обычно используют открывающую фигурную скобку ({) для обозначения точки входа расширения разметки; однако сначала проверяется следующий символ, чтобы определить, является ли он закрывающей фигурной скобкой (}).</span><span class="sxs-lookup"><span data-stu-id="e5ddb-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="e5ddb-114">Только если две фигурные скобки{}() являются смежными, они считаются escape-последовательностью.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="e5ddb-115">Если обнаружена escape-последовательность, средство чтения XAML должно обработать оставшуюся часть строки в виде строки.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="e5ddb-116">Однако если escape-последовательность применяется к элементу, имеющему преобразователь типов, строка может преобразовывать тип, когда она интерпретируется модулем записи XAML.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="e5ddb-117">Escape-последовательность не является расширением разметки и не поддерживается классом.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="e5ddb-118">Однако это соглашение о том, что средства чтения XAML (включая пользовательские средства чтения XAML) должны учитывать.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="e5ddb-119">Кавычки (") нельзя использовать в качестве escape-последовательности таким образом.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="e5ddb-120">Если необходимо задать кавычку как значение свойства для свойства, не использующего содержимое, используйте синтаксис элемента свойства и поместите кавычку как строку внутри элемента свойства или используйте сущность символов XML.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="e5ddb-121">Для свойства содержимого кавычки могут быть всего содержимого.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="e5ddb-122">Escape-последовательность ({}) часто требуется при указании типа XML, который должен включать квалификатор пространства имен в расположение, где может отображаться расширение разметки XAML.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="e5ddb-123">Это включает начало значения атрибута XAML и в расширении разметки сразу после знака равенства (=).</span><span class="sxs-lookup"><span data-stu-id="e5ddb-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="e5ddb-124">В следующем примере показаны escape-последовательности для пространства имен XML, которое отображается в начале значения атрибута XAML.</span><span class="sxs-lookup"><span data-stu-id="e5ddb-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="e5ddb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e5ddb-125">See also</span></span>

- [<span data-ttu-id="e5ddb-126">Преобразователи типов или расширения разметки для XAML</span><span class="sxs-lookup"><span data-stu-id="e5ddb-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="e5ddb-127">Сущности знаков XML и XAML</span><span class="sxs-lookup"><span data-stu-id="e5ddb-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)
