---
title: Проверка по XML-схеме (XSD) с помощью XmlSchemaSet
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 6bd7525b77d4154193b57f8e6589cb865ace5fd6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709885"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="5d246-102">Проверка по XML-схеме (XSD) с помощью XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="5d246-102">XML Schema (XSD) Validation with XmlSchemaSet</span></span>
<span data-ttu-id="5d246-103">XML-документы можно проверять на соответствие схеме XML в классе <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="5d246-103">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="5d246-104">Проверка XML-документов</span><span class="sxs-lookup"><span data-stu-id="5d246-104">Validating XML Documents</span></span>  
 <span data-ttu-id="5d246-105">Проверка XML-документов выполняется с помощью метода <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="5d246-105">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="5d246-106">Чтобы выполнить проверку XML-документа, создайте объект <xref:System.Xml.XmlReaderSettings>, содержащий схему XML, с помощью которой выполняется проверка XML-документа.</span><span class="sxs-lookup"><span data-stu-id="5d246-106">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d246-107">Пространство имен <xref:System.Xml.Schema> содержит методы расширений, которые упрощают проверку XML-дерева по файлу XSD при использовании [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) и [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5d246-107">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="5d246-108">Дополнительные сведения о проверке XML-документов с помощью LINQ to XML см. [в разделе Проверка с помощью XSD (LINQ to XMLC#) ()](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) и [инструкции по проверке с помощью XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5d246-108">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>
  
 <span data-ttu-id="5d246-109">Отдельную схему или набор схем (например, класс <xref:System.Xml.Schema.XmlSchemaSet>) можно добавить в класс <xref:System.Xml.Schema.XmlSchemaSet>, передав ее в качестве параметра метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> метод <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="5d246-109">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="5d246-110">Обратите внимание, что при проверке документа целевое пространство имен документа должно соответствовать целевому пространству имен схемы в наборе схем.</span><span class="sxs-lookup"><span data-stu-id="5d246-110">Note that when validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="5d246-111">Далее приведен пример XML-документа.</span><span class="sxs-lookup"><span data-stu-id="5d246-111">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="5d246-112">Далее приведена схема, по которой проверяется XML-документ из примера.</span><span class="sxs-lookup"><span data-stu-id="5d246-112">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="5d246-113">В последующем примере кода схема добавляется к свойству <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> объекта <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="5d246-113">In the code example that follows, the schema above is added to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="5d246-114">Объект <xref:System.Xml.XmlReaderSettings> передается в качестве параметра в метод <xref:System.Xml.XmlReader.Create%2A> объекта <xref:System.Xml.XmlReader>, который проверяет XML-документ.</span><span class="sxs-lookup"><span data-stu-id="5d246-114">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="5d246-115">Свойство <xref:System.Xml.XmlReaderSettings.ValidationType%2A> объекта <xref:System.Xml.XmlReaderSettings> устанавливается в `Schema`, чтобы включить проверку XML-документа в методе <xref:System.Xml.XmlReader.Create%2A> объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="5d246-115">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="5d246-116">Обработчик <xref:System.Xml.Schema.ValidationEventHandler> добавляется в объект <xref:System.Xml.XmlReaderSettings>, чтобы обрабатывать все события <xref:System.Xml.Schema.XmlSeverityType.Warning> или <xref:System.Xml.Schema.XmlSeverityType.Error>, вызванные в результате ошибок, найденных при проверке XML-документа и схемы.</span><span class="sxs-lookup"><span data-stu-id="5d246-116">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5d246-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d246-117">See also</span></span>

- [<span data-ttu-id="5d246-118">XmlSchemaSet для компиляции схемы</span><span class="sxs-lookup"><span data-stu-id="5d246-118">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="5d246-119">Работа с XML-схемами</span><span class="sxs-lookup"><span data-stu-id="5d246-119">Working with XML Schemas</span></span>](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
