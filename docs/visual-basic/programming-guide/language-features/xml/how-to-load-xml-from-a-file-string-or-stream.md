---
title: "Практическое руководство: загрузка XML из файла, строки или потока (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 6361ef29b88b4a05b774cf67ca0f3832a8e214fa
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="6ecb3-102">Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ecb3-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="6ecb3-103">Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока с помощью нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="6ecb3-104">Эти методы представлены в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="6ecb3-105">Загрузка XML из файла</span><span class="sxs-lookup"><span data-stu-id="6ecb3-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="6ecb3-106">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта из файла, используйте `Load` метод.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6ecb3-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="6ecb3-107">Этот метод можно использовать в качестве входа путь к файлу, текстовый поток или XML-потока.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="6ecb3-108">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29>способ заполнения <xref:System.Xml.Linq.XDocument>объектов с XML из текстового файла.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="6ecb3-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     <span data-ttu-id="6ecb3-109">[!code-vb[VbXMLSamples&#43;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6ecb3-109">[!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]</span></span>  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="6ecb3-110">Загрузка XML из строки</span><span class="sxs-lookup"><span data-stu-id="6ecb3-110">To load XML from a string</span></span>  
  
-   <span data-ttu-id="6ecb3-111">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта из строки, можно использовать `Parse` метода.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6ecb3-111">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="6ecb3-112">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>способ заполнения <xref:System.Xml.Linq.XDocument>объектов с XML из строки.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6ecb3-112">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     <span data-ttu-id="6ecb3-113">[!code-vb[VbXMLSamples&#47;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="6ecb3-113">[!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]</span></span>  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="6ecb3-114">Загрузка XML-кода из потока</span><span class="sxs-lookup"><span data-stu-id="6ecb3-114">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="6ecb3-115">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта из потока, можно использовать `Load` метода или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>метод.</xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6ecb3-115">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="6ecb3-116">В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A>способ заполнения <xref:System.Xml.Linq.XDocument>объектов с XML из XML-потока.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="6ecb3-116">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 <span data-ttu-id="6ecb3-117">[!code-vb[VbXMLSamples&#46;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="6ecb3-117">[!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecb3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6ecb3-118">See Also</span></span>  
 <span data-ttu-id="6ecb3-119"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6ecb3-119"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="6ecb3-120"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6ecb3-120"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="6ecb3-121"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6ecb3-121"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="6ecb3-122"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6ecb3-122"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="6ecb3-123"><xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6ecb3-123"><xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="6ecb3-124"> [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ecb3-124"> [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="6ecb3-125"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ecb3-125"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="6ecb3-126"> [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="6ecb3-126"> [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span></span>

