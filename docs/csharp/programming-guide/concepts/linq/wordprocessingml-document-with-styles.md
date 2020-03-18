---
title: Документ WordprocessingML со стилями3
ms.date: 07/20/2015
ms.assetid: 40e35de6-ac93-4bba-88ab-a018cbe93873
ms.openlocfilehash: 10697744680276a40fb7a175e4c04920c9e3c243
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167872"
---
# <a name="wordprocessingml-document-with-styles"></a><span data-ttu-id="bc4a2-102">Документ WordprocessingML со стилями</span><span class="sxs-lookup"><span data-stu-id="bc4a2-102">WordprocessingML Document with Styles</span></span>
<span data-ttu-id="bc4a2-103">Более сложные документы WordprocessingML обладают абзацами, которые форматированы по стилям.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-103">More complicated WordprocessingML documents have paragraphs that are formatted with styles.</span></span>  
  
 <span data-ttu-id="bc4a2-104">Необходимо сказать о составных частях документов WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-104">A few notes about the makeup of WordprocessingML documents are helpful.</span></span> <span data-ttu-id="bc4a2-105">Документы WordprocessingML размещаются в пакетах.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-105">WordprocessingML documents are stored in packages.</span></span> <span data-ttu-id="bc4a2-106">Пакеты состоят из нескольких частей (в контексте пакетов их части обладают явным значением, в сущности части - это файлы, которые заархивированы в один ZIP-файл и таким образом составляют пакет).</span><span class="sxs-lookup"><span data-stu-id="bc4a2-106">Packages have multiple parts (parts have an explicit meaning when used in the context of packages; essentially, parts are files that are zipped together to comprise a package).</span></span> <span data-ttu-id="bc4a2-107">Если документ содержит абзацы, отформатированные с помощью стилей, то также будет присутствовать часть документа, которая содержит абзацы с примененными к ним стилями.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-107">If a document contains paragraphs that are formatted with styles, there will be a document part that contains paragraphs that have styles applied to them.</span></span> <span data-ttu-id="bc4a2-108">Также будет присутствовать часть стилей, в которой содержатся стили, используемые в документе.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-108">There will also be a style part that contains the styles that are referred to by the document.</span></span>  
  
 <span data-ttu-id="bc4a2-109">При доступе к пакетам очень важно использовать для этого связи между частями, а не произвольный путь.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-109">When accessing packages, it is important that you do so through the relationships between parts, rather than using an arbitrary path.</span></span> <span data-ttu-id="bc4a2-110">Этот вопрос не рассматривается в учебнике "Обработка содержимого документа WordprocessingML", однако примеры программ, включенные в этот учебник, демонстрируют правильный подход.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-110">This issue is beyond the scope of the Manipulating Content in a WordprocessingML Document tutorial, but the example programs that are included in this tutorial demonstrate the correct approach.</span></span>  
  
## <a name="a-document-that-uses-styles"></a><span data-ttu-id="bc4a2-111">Документ, в котором используются стили</span><span class="sxs-lookup"><span data-stu-id="bc4a2-111">A Document that Uses Styles</span></span>  
 <span data-ttu-id="bc4a2-112">Пример WordML, приводимый в разделе [Форма документов WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md), очень простой.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-112">The WordML example presented in the [Shape of WordprocessingML Documents (C#)](./shape-of-wordprocessingml-documents.md) topic is a very simple one.</span></span> <span data-ttu-id="bc4a2-113">Следующий документ более сложный: он содержит абзацы, отформатированные с использованием стилей.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-113">The following document is more complicated: It has paragraphs that are formatted with styles.</span></span> <span data-ttu-id="bc4a2-114">Самый простой способ увидеть XML, который составляет XML-документ Office Open, состоит в том, чтобы запустить [Пример, выводящий части документа в формате Office Open XML (C#)](./example-that-outputs-office-open-xml-document-parts.md).</span><span class="sxs-lookup"><span data-stu-id="bc4a2-114">The easiest way to see the XML that makes up an Office Open XML document is to run the [Example that Outputs Office Open XML Document Parts (C#)](./example-that-outputs-office-open-xml-document-parts.md).</span></span>  
  
 <span data-ttu-id="bc4a2-115">В следующем документе первый абзац имеет стиль `Heading1`.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-115">In the following document, the first paragraph has the style `Heading1`.</span></span> <span data-ttu-id="bc4a2-116">Имеется несколько абзацев со стилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-116">There are a number of paragraphs that have the default style.</span></span> <span data-ttu-id="bc4a2-117">Также имеется несколько абзацев со стилем `Code`.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-117">There are also a number of paragraphs that have the style `Code`.</span></span> <span data-ttu-id="bc4a2-118">Благодаря этой относительной сложности синтаксический анализ этого документа при помощи LINQ to XML более интересен.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-118">Because of this relative complexity, this is a more interesting document to parse with LINQ to XML.</span></span>  
  
 <span data-ttu-id="bc4a2-119">В абзацах, стиль которых отличен от стиля по умолчанию, элементы абзацев обладают дочерним элементом `w:pPr`, который в свою очередь также обладает дочерним элементом `w:pStyle`.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-119">In those paragraphs with non-default styles, the paragraph elements have a child element named `w:pPr`, which in turn has a child element `w:pStyle`.</span></span> <span data-ttu-id="bc4a2-120">У этого элемента имеется атрибут `w:val`, который содержит имя стиля.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-120">That element has an attribute, `w:val`, which contains the style name.</span></span> <span data-ttu-id="bc4a2-121">Если абзац имеет стиль по умолчанию, это означает, что у него отсутствует дочерний элемент `w:p.Pr`.</span><span class="sxs-lookup"><span data-stu-id="bc4a2-121">If the paragraph has the default style, it means that the paragraph element does not have a `w:p.Pr` child element.</span></span>  
  
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
