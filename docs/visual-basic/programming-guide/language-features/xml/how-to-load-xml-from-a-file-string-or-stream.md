---
title: "Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 572e34b1cd4813fad35e6afaf2ec3d0d9dac470a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="fe59f-102">Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe59f-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="fe59f-103">Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимое из внешнего источника, например файла, строки или потока с помощью нескольких методов.</span><span class="sxs-lookup"><span data-stu-id="fe59f-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="fe59f-104">В следующих примерах показаны эти методы.</span><span class="sxs-lookup"><span data-stu-id="fe59f-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="fe59f-105">Чтобы загрузить XML из файла</span><span class="sxs-lookup"><span data-stu-id="fe59f-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="fe59f-106">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из файла, используйте `Load` метод.</span><span class="sxs-lookup"><span data-stu-id="fe59f-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="fe59f-107">Этот метод можно использовать в качестве входа путь к файлу, текстовый поток или XML-поток.</span><span class="sxs-lookup"><span data-stu-id="fe59f-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="fe59f-108">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> метод для заполнения <xref:System.Xml.Linq.XDocument> объекта с XML из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="fe59f-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="fe59f-109">Чтобы загрузить XML из строки</span><span class="sxs-lookup"><span data-stu-id="fe59f-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="fe59f-110">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из строки, можно использовать `Parse` метода.</span><span class="sxs-lookup"><span data-stu-id="fe59f-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="fe59f-111">В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> метод для заполнения <xref:System.Xml.Linq.XDocument> объекта с XML из строки.</span><span class="sxs-lookup"><span data-stu-id="fe59f-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="fe59f-112">Чтобы загрузить XML из потока</span><span class="sxs-lookup"><span data-stu-id="fe59f-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="fe59f-113">Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из потока, можно использовать `Load` метода или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="fe59f-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="fe59f-114">В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> метод для заполнения <xref:System.Xml.Linq.XDocument> объект с XML из XML-потока.</span><span class="sxs-lookup"><span data-stu-id="fe59f-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fe59f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fe59f-115">See Also</span></span>  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fe59f-116">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="fe59f-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="fe59f-117">XML</span><span class="sxs-lookup"><span data-stu-id="fe59f-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="fe59f-118">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe59f-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
