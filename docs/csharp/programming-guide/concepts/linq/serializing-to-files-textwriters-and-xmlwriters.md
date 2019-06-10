---
title: Сериализация в файлы и объекты TextWriters и XmlWriters1
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: c74dc7f429e4ae27f08f7acb6b3a6c39161aac71
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66483550"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="f141f-102">Сериализация в файлы и объекты TextWriters и XmlWriters</span><span class="sxs-lookup"><span data-stu-id="f141f-102">Serializing to Files, TextWriters, and XmlWriters</span></span>

<span data-ttu-id="f141f-103">XML-деревья можно сериализовать для <xref:System.IO.File>, <xref:System.IO.TextWriter> или для <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="f141f-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="f141f-104">Любой компонент XML, включая <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement>, можно сериализовать для строки с помощью метода `ToString`.</span><span class="sxs-lookup"><span data-stu-id="f141f-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>

<span data-ttu-id="f141f-105">Если в процессе сериализации в строку необходимо подавить форматирование, эту задачу можно решить с помощью метода <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f141f-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f141f-106">При выполнении сериализации для файла поведение по умолчанию заключается в форматировании (посредством создания отступов) результирующего XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f141f-106">The default behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="f141f-107">При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="f141f-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="f141f-108">Для выполнения сериализации с форматированием нужно использовать одну из перегрузок следующих методов, не принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="f141f-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="f141f-109">Если необходимо воздержаться от создания отступов и сохранить не имеющие значения пробелы в XML-дереве, нужно использовать одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="f141f-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="f141f-110">Примеры см. в следующем разделе справки.</span><span class="sxs-lookup"><span data-stu-id="f141f-110">For examples, see the appropriate reference topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="f141f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f141f-111">See also</span></span>

- [<span data-ttu-id="f141f-112">Сериализация XML-деревьев (C#)</span><span class="sxs-lookup"><span data-stu-id="f141f-112">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
