---
title: Практическое руководство. Загрузка XML-кода из файла, строки или потока
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330961"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="90f52-102">Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90f52-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="90f52-103">Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока, с помощью нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="90f52-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="90f52-104">Эти методы показаны в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="90f52-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="90f52-105">Загрузка XML из файла</span><span class="sxs-lookup"><span data-stu-id="90f52-105">To load XML from a file</span></span>

<span data-ttu-id="90f52-106">Для заполнения XML-литерала, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из файла, используйте метод `Load`.</span><span class="sxs-lookup"><span data-stu-id="90f52-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="90f52-107">Этот метод может принимать в качестве входных данных путь к файлу, поток текста или поток XML.</span><span class="sxs-lookup"><span data-stu-id="90f52-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="90f52-108">В следующем примере кода показано использование метода <xref:System.Xml.Linq.XDocument.Load%28System.String%29> для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="90f52-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="90f52-109">Загрузка XML из строки</span><span class="sxs-lookup"><span data-stu-id="90f52-109">To load XML from a string</span></span>

<span data-ttu-id="90f52-110">Для заполнения XML-литерала, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из строки, можно использовать метод `Parse`.</span><span class="sxs-lookup"><span data-stu-id="90f52-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="90f52-111">В следующем примере кода показано использование метода <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из строки.</span><span class="sxs-lookup"><span data-stu-id="90f52-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="90f52-112">Загрузка XML из потока</span><span class="sxs-lookup"><span data-stu-id="90f52-112">To load XML from a stream</span></span>

<span data-ttu-id="90f52-113">Чтобы заполнить литерал XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объект из потока, можно использовать метод `Load` или метод <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90f52-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="90f52-114">В следующем примере кода показано использование метода <xref:System.Xml.Linq.XNode.ReadFrom%2A> для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из потока XML.</span><span class="sxs-lookup"><span data-stu-id="90f52-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="90f52-115">См. также</span><span class="sxs-lookup"><span data-stu-id="90f52-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="90f52-116">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="90f52-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="90f52-117">XML</span><span class="sxs-lookup"><span data-stu-id="90f52-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="90f52-118">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90f52-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
