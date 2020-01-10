---
title: Ввод XmlDocument в XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
ms.openlocfilehash: c7819c3cb6b1430dcdb8a78c43f7138f64e691a8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709846"
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="56ebb-102">Ввод XmlDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="56ebb-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="56ebb-103">Класс <xref:System.Xml.XmlDocument> представляет возможности изменения XML-документа.</span><span class="sxs-lookup"><span data-stu-id="56ebb-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="56ebb-104">Если нужно изменить XML-документ перед передачей методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>, загрузите XML-документ в объект <xref:System.Xml.XmlDocument>, измените его и отправьте в объект <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="56ebb-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56ebb-105">Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="56ebb-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="56ebb-106">Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="56ebb-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="56ebb-107">См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="56ebb-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="56ebb-108">Класс <xref:System.Xml.XmlDocument> реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, поэтому документ можно передать в метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> после изменения.</span><span class="sxs-lookup"><span data-stu-id="56ebb-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="56ebb-109">Из-за возможности изменения объекта <xref:System.Xml.XmlDocument> при использовании класса <xref:System.Xml.XmlDocument> в качестве входных данных преобразования быстродействие ниже, чем при использовании класса <xref:System.Xml.XPath.XPathDocument> для XSLT-преобразований, так как класс <xref:System.Xml.XPath.XPathDocument> оптимизирован для запросов XPath благодаря внутреннему хранению.</span><span class="sxs-lookup"><span data-stu-id="56ebb-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56ebb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="56ebb-110">Example</span></span>  
 <span data-ttu-id="56ebb-111">В следующем примере кода показано, как можно предоставить объект <xref:System.Xml.XmlDocument> объекту <xref:System.Xml.Xsl.XslTransform> и передать вывод в объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="56ebb-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a><span data-ttu-id="56ebb-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="56ebb-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- [<span data-ttu-id="56ebb-113">XSLT-преобразования с помощью класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="56ebb-113">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="56ebb-114">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="56ebb-114">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="56ebb-115">XPathNavigator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="56ebb-115">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [<span data-ttu-id="56ebb-116">XPathNodeIterator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="56ebb-116">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="56ebb-117">Ввод XPathDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="56ebb-117">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="56ebb-118">Ввод XmlDataDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="56ebb-118">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
