---
title: "Оператор GetXmlNamespace (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d6f977ab8c0b7dfb2dee936436ef4ec8530ba8f6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="7b6e3-102">Оператор GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b6e3-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="7b6e3-103">Возвращает <xref:System.Xml.Linq.XNamespace>объекта, который соответствует указанным префиксом пространства имен XML.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="7b6e3-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b6e3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b6e3-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="7b6e3-105">Части</span><span class="sxs-lookup"><span data-stu-id="7b6e3-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="7b6e3-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-106">Optional.</span></span> <span data-ttu-id="7b6e3-107">Строка, определяющая префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="7b6e3-108">Если указано, эта строка должна быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="7b6e3-109">Дополнительные сведения см. в разделе [имена объявленных элементов XML и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="7b6e3-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="7b6e3-110">Если префикс не указан, возвращается пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="7b6e3-111">Если пространство имен по умолчанию не задано, возвращается пустое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b6e3-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b6e3-112">Return Value</span></span>  
 <span data-ttu-id="7b6e3-113"><xref:System.Xml.Linq.XNamespace>, Соответствующий префикс пространства имен XML.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="7b6e3-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b6e3-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b6e3-114">Remarks</span></span>  
 <span data-ttu-id="7b6e3-115">`GetXmlNamespace` Оператор возвращает <xref:System.Xml.Linq.XNamespace>, соответствующий префикс пространства имен XML `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="7b6e3-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="7b6e3-116">Можно использовать префиксы пространства имен XML непосредственно в XML-литералы и свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="7b6e3-117">Тем не менее, необходимо использовать `GetXmlNamespace` оператор преобразования префикс пространства имен для <xref:System.Xml.Linq.XNamespace>объекта перед использованием в коде.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="7b6e3-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="7b6e3-118">После добавления имени неполное элемента для <xref:System.Xml.Linq.XNamespace>полное имя объекта <xref:System.Xml.Linq.XName>объекта, который многие [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] методы требуют.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="7b6e3-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b6e3-119">Пример</span><span class="sxs-lookup"><span data-stu-id="7b6e3-119">Example</span></span>  
 <span data-ttu-id="7b6e3-120">В следующем примере выполняется импорт `ns` как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="7b6e3-121">Затем используется префикс пространства имен для создания литерала XML и доступа к первым дочерним узлом, который имеет полное имя `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="7b6e3-122">Он затем передает этот дочерний узел для `ShowName` подпрограмму, которая создает полное имя с помощью `GetXmlNamespace` оператор.</span><span class="sxs-lookup"><span data-stu-id="7b6e3-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="7b6e3-123">`ShowName` Подпрограммы передает проверенное имя <xref:System.Xml.Linq.XNode.Ancestors%2A>метод, чтобы получить родительский `ns:contact` узла.</xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="7b6e3-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 <span data-ttu-id="7b6e3-124">[!code-vb[VbXMLSamples&#38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b6e3-124">[!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="7b6e3-125">При вызове метода `TestGetXmlNamespace.RunSample()`, отображается окно сообщения, содержащее следующий текст:</span><span class="sxs-lookup"><span data-stu-id="7b6e3-125">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="7b6e3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7b6e3-126">See Also</span></span>  
 <span data-ttu-id="7b6e3-127">[Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="7b6e3-127">[Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="7b6e3-128"> [Доступ к XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="7b6e3-128"> [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span></span>
