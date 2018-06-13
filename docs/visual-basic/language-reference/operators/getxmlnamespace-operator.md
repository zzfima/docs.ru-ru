---
title: Оператор GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: e21cf160d10f308990894d1a85c4f5d05b90f68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603487"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="727ae-102">Оператор GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="727ae-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="727ae-103">Возвращает <xref:System.Xml.Linq.XNamespace> объекта, который соответствует указанным префиксом пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="727ae-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="727ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="727ae-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="727ae-105">Части</span><span class="sxs-lookup"><span data-stu-id="727ae-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="727ae-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="727ae-106">Optional.</span></span> <span data-ttu-id="727ae-107">Строка, определяющая префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="727ae-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="727ae-108">Если указано, эта строка должна быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="727ae-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="727ae-109">Дополнительные сведения см. в разделе [имена из объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="727ae-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="727ae-110">Если префикс не указан, возвращается пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="727ae-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="727ae-111">Если пространство имен по умолчанию не задано, возвращается пустое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="727ae-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="727ae-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="727ae-112">Return Value</span></span>  
 <span data-ttu-id="727ae-113"><xref:System.Xml.Linq.XNamespace> Объект, соответствующий префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="727ae-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="727ae-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="727ae-114">Remarks</span></span>  
 <span data-ttu-id="727ae-115">`GetXmlNamespace` Оператор возвращает <xref:System.Xml.Linq.XNamespace> объект, соответствующий префикс пространства имен XML `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="727ae-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="727ae-116">Можно использовать префиксы пространства имен XML непосредственно в XML-литералы и свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="727ae-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="727ae-117">Тем не менее, необходимо использовать `GetXmlNamespace` оператор преобразования префикс пространства имен для <xref:System.Xml.Linq.XNamespace> объекта перед его можно использовать в коде.</span><span class="sxs-lookup"><span data-stu-id="727ae-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="727ae-118">После добавления имени неизвестного элемента для <xref:System.Xml.Linq.XNamespace> объекта для получения полного имени <xref:System.Xml.Linq.XName> объекта, который многие [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методы требуют.</span><span class="sxs-lookup"><span data-stu-id="727ae-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="727ae-119">Пример</span><span class="sxs-lookup"><span data-stu-id="727ae-119">Example</span></span>  
 <span data-ttu-id="727ae-120">В следующем примере выполняется импорт `ns` как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="727ae-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="727ae-121">Затем используется префикс пространства имен для создания литерала XML и доступа к первым дочерним узлом, который имеет полное имя `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="727ae-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="727ae-122">Он затем передает этот дочерний узел для `ShowName` подпрограмму, которая создает полное имя с помощью `GetXmlNamespace` оператор.</span><span class="sxs-lookup"><span data-stu-id="727ae-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="727ae-123">`ShowName` Подпрограммы полного имени, которое передает <xref:System.Xml.Linq.XNode.Ancestors%2A> метод нужно получить родительский `ns:contact` узла.</span><span class="sxs-lookup"><span data-stu-id="727ae-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 <span data-ttu-id="727ae-124">При вызове `TestGetXmlNamespace.RunSample()`, он отображает окно сообщения, содержащее следующий текст:</span><span class="sxs-lookup"><span data-stu-id="727ae-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="727ae-125">См. также</span><span class="sxs-lookup"><span data-stu-id="727ae-125">See Also</span></span>  
 [<span data-ttu-id="727ae-126">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="727ae-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="727ae-127">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="727ae-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
