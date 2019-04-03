---
title: Практическое руководство. Загрузить XML из файла, строки или Stream (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 2b9da2062068ef25c5df97ef19b1502999ea78ed
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832142"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="2fbc6-102">Практическое руководство. Загрузить XML из файла, строки или Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fbc6-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="2fbc6-103">Можно создать [XML-литералов](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнять их с содержимым из внешнего источника, например файла, строку или поток с помощью нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="2fbc6-104">Эти методы представлены в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="2fbc6-105">Загрузить XML из файла</span><span class="sxs-lookup"><span data-stu-id="2fbc6-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="2fbc6-106">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объект из файла, используйте `Load` метод.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="2fbc6-107">Этот метод может принимать в качестве входных данных путь к файлу, текстовый поток или XML-поток.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="2fbc6-108">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> способ заполнения <xref:System.Xml.Linq.XDocument> объект с XML из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="2fbc6-109">Загрузить XML из строки</span><span class="sxs-lookup"><span data-stu-id="2fbc6-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="2fbc6-110">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из строки, можно использовать `Parse` метод.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="2fbc6-111">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> способ заполнения <xref:System.Xml.Linq.XDocument> объект с XML из строки.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="2fbc6-112">Загрузить XML из потока</span><span class="sxs-lookup"><span data-stu-id="2fbc6-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="2fbc6-113">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из потока, можно использовать `Load` метод или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="2fbc6-114">В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> способ заполнения <xref:System.Xml.Linq.XDocument> объект с XML из XML-потока.</span><span class="sxs-lookup"><span data-stu-id="2fbc6-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="2fbc6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2fbc6-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2fbc6-116">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="2fbc6-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2fbc6-117">XML</span><span class="sxs-lookup"><span data-stu-id="2fbc6-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="2fbc6-118">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fbc6-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
