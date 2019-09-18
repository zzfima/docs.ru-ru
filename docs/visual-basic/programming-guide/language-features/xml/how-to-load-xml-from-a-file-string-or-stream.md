---
title: Практическое руководство. Загрузка XML из файла, строки или потока (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: ba88ae19abc216a318d6c2069ab0846d5db8a346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054166"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="e2c15-102">Практическое руководство. Загрузка XML из файла, строки или потока (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2c15-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="e2c15-103">Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока, с помощью нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="e2c15-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="e2c15-104">Эти методы показаны в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="e2c15-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="e2c15-105">Загрузка XML из файла</span><span class="sxs-lookup"><span data-stu-id="e2c15-105">To load XML from a file</span></span>

<span data-ttu-id="e2c15-106">Чтобы заполнить XML-литерал, например <xref:System.Xml.Linq.XElement> объект или <xref:System.Xml.Linq.XDocument> , из файла, используйте `Load` метод.</span><span class="sxs-lookup"><span data-stu-id="e2c15-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="e2c15-107">Этот метод может принимать в качестве входных данных путь к файлу, поток текста или поток XML.</span><span class="sxs-lookup"><span data-stu-id="e2c15-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="e2c15-108">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="e2c15-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="e2c15-109">Загрузка XML из строки</span><span class="sxs-lookup"><span data-stu-id="e2c15-109">To load XML from a string</span></span>

<span data-ttu-id="e2c15-110">Для заполнения XML-литерала <xref:System.Xml.Linq.XElement> `Parse` , такого как объект <xref:System.Xml.Linq.XDocument> или, из строки можно использовать метод.</span><span class="sxs-lookup"><span data-stu-id="e2c15-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="e2c15-111">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из строки.</span><span class="sxs-lookup"><span data-stu-id="e2c15-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="e2c15-112">Загрузка XML из потока</span><span class="sxs-lookup"><span data-stu-id="e2c15-112">To load XML from a stream</span></span>

<span data-ttu-id="e2c15-113">Для заполнения XML- <xref:System.Xml.Linq.XElement> литерала `Load` , такого как объект <xref:System.Xml.Linq.XDocument> или, из потока можно <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> использовать метод или.</span><span class="sxs-lookup"><span data-stu-id="e2c15-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e2c15-114">В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML-потоком из XML-потока.</span><span class="sxs-lookup"><span data-stu-id="e2c15-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="e2c15-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e2c15-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e2c15-116">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="e2c15-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e2c15-117">XML</span><span class="sxs-lookup"><span data-stu-id="e2c15-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="e2c15-118">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2c15-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
