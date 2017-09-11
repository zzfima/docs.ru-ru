---
title: "Сериализация в файлы и объекты TextWriters и XmlWriters3 | Документы Microsoft"
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
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f8f8672004b0704b00ff60e5b58256f664bcbd82
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="0162a-102">Сериализация в файлы и объекты TextWriters и XmlWriters</span><span class="sxs-lookup"><span data-stu-id="0162a-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="0162a-103">Можно сериализовать XML-деревья в <xref:System.IO.File>, <xref:System.IO.TextWriter>, или <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="0162a-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="0162a-104">Можно сериализовать любой компонент XML, включая <xref:System.Xml.Linq.XDocument>и <xref:System.Xml.Linq.XElement>, в строку с помощью `ToString` метод.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="0162a-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="0162a-105">Если необходимо отключить форматирование при сериализации в строку, можно использовать <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>метода.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0162a-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="0162a-106">Установка9600 поведение при сериализации для файла состоит в форматировании (посредством создания отступов) результирующего XML-документа.</span><span class="sxs-lookup"><span data-stu-id="0162a-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="0162a-107">При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="0162a-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="0162a-108">Для выполнения сериализации с форматированием, используйте одну из перегрузок следующих методов, которые не принимают <xref:System.Xml.Linq.SaveOptions>в качестве аргумента:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="0162a-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="0162a-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0162a-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="0162a-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0162a-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="0162a-111">Если необходимо воздержаться от создания отступов и сохранять незначащие пробелы в XML-дерево, используйте одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions>в качестве аргумента:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="0162a-111">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="0162a-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0162a-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="0162a-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0162a-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="0162a-114">Примеры см. в следующем разделе справки.</span><span class="sxs-lookup"><span data-stu-id="0162a-114">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0162a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0162a-115">See Also</span></span>  
 [<span data-ttu-id="0162a-116">Сериализация деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0162a-116">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
