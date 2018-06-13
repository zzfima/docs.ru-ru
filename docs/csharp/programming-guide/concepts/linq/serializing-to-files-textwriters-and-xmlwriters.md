---
title: Сериализация в файлы и объекты TextWriters и XmlWriters1
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: 903e6f5b6a8cd88c140e6759136301a6305cee2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330214"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="51910-102">Сериализация в файлы и объекты TextWriters и XmlWriters</span><span class="sxs-lookup"><span data-stu-id="51910-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="51910-103">XML-деревья можно сериализовать для <xref:System.IO.File>, <xref:System.IO.TextWriter> или для <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="51910-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="51910-104">Любой компонент XML, включая <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement>, можно сериализовать для строки с помощью метода `ToString`.</span><span class="sxs-lookup"><span data-stu-id="51910-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="51910-105">Если в процессе сериализации в строку необходимо подавить форматирование, эту задачу можно решить с помощью метода <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51910-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="51910-106">При выполнении сериализации для файла характер действий по умолчанию состоит в форматировании результирующего XML-документа посредством создания отступов.</span><span class="sxs-lookup"><span data-stu-id="51910-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="51910-107">При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="51910-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="51910-108">Для выполнения сериализации с форматированием нужно использовать одну из перегрузок следующих методов, не принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="51910-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="51910-109">Если необходимо воздержаться от создания отступов и сохранить не имеющие значения пробелы в XML-дереве, нужно использовать одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="51910-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="51910-110">Примеры см. в следующем разделе справки.</span><span class="sxs-lookup"><span data-stu-id="51910-110">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51910-111">См. также</span><span class="sxs-lookup"><span data-stu-id="51910-111">See Also</span></span>  
 [<span data-ttu-id="51910-112">Сериализация XML-деревьев (C#)</span><span class="sxs-lookup"><span data-stu-id="51910-112">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
