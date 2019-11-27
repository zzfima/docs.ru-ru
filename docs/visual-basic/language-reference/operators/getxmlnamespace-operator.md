---
title: Оператор GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 4d6e738f4e3a47d73e37c395dd74fe19e99d81bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353194"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="9ed6a-102">Оператор GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ed6a-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="9ed6a-103">Возвращает объект <xref:System.Xml.Linq.XNamespace>, соответствующий указанному префиксу пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ed6a-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="9ed6a-105">Части</span><span class="sxs-lookup"><span data-stu-id="9ed6a-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="9ed6a-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-106">Optional.</span></span> <span data-ttu-id="9ed6a-107">Строка, определяющая префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="9ed6a-108">Если указано, эта строка должна быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="9ed6a-109">Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="9ed6a-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="9ed6a-110">Если префикс не указан, возвращается пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="9ed6a-111">Если пространство имен по умолчанию не указано, возвращается пустое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ed6a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9ed6a-112">Return Value</span></span>  
 <span data-ttu-id="9ed6a-113">Объект <xref:System.Xml.Linq.XNamespace>, соответствующий префиксу пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ed6a-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="9ed6a-114">Remarks</span></span>  
 <span data-ttu-id="9ed6a-115">Оператор `GetXmlNamespace` получает объект <xref:System.Xml.Linq.XNamespace>, соответствующий префиксу пространства имен XML `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="9ed6a-116">Префиксы пространства имен XML можно использовать непосредственно в XML-литералах и свойствах осей XML.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="9ed6a-117">Однако необходимо использовать оператор `GetXmlNamespace` для преобразования префикса пространства имен в объект <xref:System.Xml.Linq.XNamespace>, прежде чем его можно будет использовать в коде.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="9ed6a-118">Можно добавить неполное имя элемента в <xref:System.Xml.Linq.XNamespace> объект, чтобы получить полный <xref:System.Xml.Linq.XName> объект, который требуется многим [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методам.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ed6a-119">Пример</span><span class="sxs-lookup"><span data-stu-id="9ed6a-119">Example</span></span>  
 <span data-ttu-id="9ed6a-120">В следующем примере выполняется импорт `ns` как префикса пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="9ed6a-121">Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="9ed6a-122">Затем этот дочерний узел передается в подпрограммы `ShowName`, которая формирует полное имя с помощью оператора `GetXmlNamespace`.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="9ed6a-123">Затем `ShowName` подпрограммы передает полное имя методу <xref:System.Xml.Linq.XNode.Ancestors%2A>, чтобы получить родительский узел `ns:contact`.</span><span class="sxs-lookup"><span data-stu-id="9ed6a-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="9ed6a-124">При вызове `TestGetXmlNamespace.RunSample()`отображается окно сообщения, содержащее следующий текст:</span><span class="sxs-lookup"><span data-stu-id="9ed6a-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="9ed6a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9ed6a-125">See also</span></span>

- [<span data-ttu-id="9ed6a-126">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="9ed6a-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="9ed6a-127">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ed6a-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
