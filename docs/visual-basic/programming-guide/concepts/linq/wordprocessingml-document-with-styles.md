---
title: Документ WordprocessingML со Styles2
ms.date: 07/20/2015
ms.assetid: a9136e4d-c368-4661-8049-7d45c679a236
ms.openlocfilehash: 0f6ca610d67418582e3426bb911b26eb846070da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648825"
---
# <a name="wordprocessingml-document-with-styles"></a><span data-ttu-id="649fc-102">Документ WordprocessingML со стилями</span><span class="sxs-lookup"><span data-stu-id="649fc-102">WordprocessingML Document with Styles</span></span>
<span data-ttu-id="649fc-103">Более сложные документы WordprocessingML обладают абзацами, которые форматированы по стилям.</span><span class="sxs-lookup"><span data-stu-id="649fc-103">More complicated WordprocessingML documents have paragraphs that are formatted with styles.</span></span>  
  
 <span data-ttu-id="649fc-104">Необходимо сказать о составных частях документов WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="649fc-104">A few notes about the makeup of WordprocessingML documents are helpful.</span></span> <span data-ttu-id="649fc-105">Документы WordprocessingML размещаются в пакетах.</span><span class="sxs-lookup"><span data-stu-id="649fc-105">WordprocessingML documents are stored in packages.</span></span> <span data-ttu-id="649fc-106">Пакеты состоят из нескольких частей (в контексте пакетов их части обладают явным значением, в сущности части - это файлы, которые заархивированы в один ZIP-файл и таким образом составляют пакет).</span><span class="sxs-lookup"><span data-stu-id="649fc-106">Packages have multiple parts (parts have an explicit meaning when used in the context of packages; essentially, parts are files that are zipped together to comprise a package).</span></span> <span data-ttu-id="649fc-107">Если документ содержит абзацы, отформатированные с помощью стилей, то также будет присутствовать часть документа, которая содержит абзацы с примененными к ним стилями.</span><span class="sxs-lookup"><span data-stu-id="649fc-107">If a document contains paragraphs that are formatted with styles, there will be a document part that contains paragraphs that have styles applied to them.</span></span> <span data-ttu-id="649fc-108">Также будет присутствовать часть стилей, в которой содержатся стили, используемые в документе.</span><span class="sxs-lookup"><span data-stu-id="649fc-108">There will also be a style part that contains the styles that are referred to by the document.</span></span>  
  
 <span data-ttu-id="649fc-109">При доступе к пакетам очень важно использовать для этого связи между частями, а не произвольный путь.</span><span class="sxs-lookup"><span data-stu-id="649fc-109">When accessing packages, it is important that you do so through the relationships between parts, rather than using an arbitrary path.</span></span> <span data-ttu-id="649fc-110">Этот вопрос не рассматривается в учебнике "Обработка содержимого документа WordprocessingML", однако примеры программ, включенные в этот учебник, демонстрируют правильный подход.</span><span class="sxs-lookup"><span data-stu-id="649fc-110">This issue is beyond the scope of the Manipulating Content in a WordprocessingML Document tutorial, but the example programs that are included in this tutorial demonstrate the correct approach.</span></span>  
  
## <a name="a-document-that-uses-styles"></a><span data-ttu-id="649fc-111">Документ, в котором используются стили</span><span class="sxs-lookup"><span data-stu-id="649fc-111">A Document that Uses Styles</span></span>  
 <span data-ttu-id="649fc-112">Пример WordML, приводимый в [форма документов WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md) раздел является очень простым.</span><span class="sxs-lookup"><span data-stu-id="649fc-112">The WordML example presented in the [Shape of WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md) topic is a very simple one.</span></span> <span data-ttu-id="649fc-113">Следующий документ более сложный: он содержит абзацы, отформатированные с использованием стилей.</span><span class="sxs-lookup"><span data-stu-id="649fc-113">The following document is more complicated: It has paragraphs that are formatted with styles.</span></span> <span data-ttu-id="649fc-114">Самым простым способом является XML, содержащийся в документ Office Open XML для запуска [пример, выходные данные Office Open XML-документа частей (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/example-that-outputs-office-open-xml-document-parts.md).</span><span class="sxs-lookup"><span data-stu-id="649fc-114">The easiest way to see the XML that makes up an Office Open XML document is to run the [Example that Outputs Office Open XML Document Parts (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/example-that-outputs-office-open-xml-document-parts.md).</span></span>  
  
 <span data-ttu-id="649fc-115">В следующем документе первый абзац имеет стиль `Heading1`.</span><span class="sxs-lookup"><span data-stu-id="649fc-115">In the following document, the first paragraph has the style `Heading1`.</span></span> <span data-ttu-id="649fc-116">Имеется несколько абзацев со стилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="649fc-116">There are a number of paragraphs that have the default style.</span></span> <span data-ttu-id="649fc-117">Также имеется несколько абзацев со стилем `Code`.</span><span class="sxs-lookup"><span data-stu-id="649fc-117">There are also a number of paragraphs that have the style `Code`.</span></span> <span data-ttu-id="649fc-118">Благодаря этой относительной сложности синтаксический анализ этого документа при помощи LINQ to XML более интересен.</span><span class="sxs-lookup"><span data-stu-id="649fc-118">Because of this relative complexity, this is a more interesting document to parse with LINQ to XML.</span></span>  
  
 <span data-ttu-id="649fc-119">В абзацах, стиль которых отличен от стиля по умолчанию, элементы абзацев обладают дочерним элементом `w:pPr`, который в свою очередь также обладает дочерним элементом `w:pStyle`.</span><span class="sxs-lookup"><span data-stu-id="649fc-119">In those paragraphs with non-default styles, the paragraph elements have a child element named `w:pPr`, which in turn has a child element `w:pStyle`.</span></span> <span data-ttu-id="649fc-120">У этого элемента имеется атрибут `w:val`, который содержит имя стиля.</span><span class="sxs-lookup"><span data-stu-id="649fc-120">That element has an attribute, `w:val`, which contains the style name.</span></span> <span data-ttu-id="649fc-121">Если абзац имеет стиль по умолчанию, это означает, что у него отсутствует дочерний элемент `w:p.Pr`.</span><span class="sxs-lookup"><span data-stu-id="649fc-121">If the paragraph has the default style, it means that the paragraph element does not have a `w:p.Pr` child element.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:document  
    xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:o="urn:schemas-microsoft-com:office:office"  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
    xmlns:v="urn:schemas-microsoft-com:vml"  
    xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
    xmlns:w10="urn:schemas-microsoft-com:office:word"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
    xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Heading1" />  
      </w:pPr>  
      <w:r>  
        <w:t>Parsing WordprocessingML with LINQ to XML</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>The following example prints to the console.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>using System;</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>class Program {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    public static void </w:t>  
      </w:r>  
      <w:smartTag w:uri="urn:schemas-microsoft-com:office:smarttags" w:element="place">  
        <w:r w:rsidRPr="00876F34">  
          <w:t>Main</w:t>  
        </w:r>  
      </w:smartTag>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>(string[] args) {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">        Console.WriteLine("Hello World");</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    }</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>}</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>This example produces the following output:</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>Hello World</w:t>  
      </w:r>  
    </w:p>  
    <w:sectPr w:rsidR="00A75AE0" w:rsidSect="00A75AE0">  
      <w:pgSz w:w="12240" w:h="15840" />  
      <w:pgMar w:top="1440" w:right="1800" w:bottom="1440" w:left="1800" w:header="720" w:footer="720" w:gutter="0" />  
      <w:cols w:space="720" />  
      <w:docGrid w:linePitch="360" />  
    </w:sectPr>  
  </w:body>  
</w:document>  
```  
  
## <a name="see-also"></a><span data-ttu-id="649fc-122">См. также</span><span class="sxs-lookup"><span data-stu-id="649fc-122">See Also</span></span>  
 [<span data-ttu-id="649fc-123">Сведения об Office открывать документы WordprocessingML XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="649fc-123">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
