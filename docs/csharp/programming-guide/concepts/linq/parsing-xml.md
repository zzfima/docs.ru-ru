---
title: Анализ XML (C#)
ms.date: 07/20/2015
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
ms.openlocfilehash: f19e5a316621262bfe0f3fb56a13275336cf763f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617048"
---
# <a name="parsing-xml-c"></a><span data-ttu-id="97c5c-102">Анализ XML (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-102">Parsing XML (C#)</span></span>
<span data-ttu-id="97c5c-103">Подразделы в данном разделе описывают синтаксический анализ XML-документов.</span><span class="sxs-lookup"><span data-stu-id="97c5c-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97c5c-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="97c5c-104">In This Section</span></span>  
  
|<span data-ttu-id="97c5c-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="97c5c-105">Topic</span></span>|<span data-ttu-id="97c5c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="97c5c-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="97c5c-107">Практическое руководство. Анализ строки (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-107">How to: Parse a String (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="97c5c-108">Показывает, как анализировать строку для создания XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="97c5c-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="97c5c-109">Практическое руководство. Загрузка XML-кода из файла (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-109">How to: Load XML from a File (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="97c5c-110">Показывает, как загружать XML из URI-кода с помощью метода <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="97c5c-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="97c5c-111">Сохранение пробелов при загрузке и анализе XML</span><span class="sxs-lookup"><span data-stu-id="97c5c-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="97c5c-112">Описывает, как управлять поведением пробелов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] при загрузке XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="97c5c-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="97c5c-113">Практическое руководство. Перехват ошибок анализа (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-113">How to: Catch Parsing Errors (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="97c5c-114">Показывает, как выявлять плохо отформатированные или недопустимые коды XML.</span><span class="sxs-lookup"><span data-stu-id="97c5c-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="97c5c-115">Практическое руководство. Создание дерева из XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-115">How to: Create a Tree from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="97c5c-116">Показывает, как создавать XML-дерево непосредственно из <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="97c5c-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="97c5c-117">Практическое руководство. Потоковая передача фрагментов XML из XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-117">How to: Stream XML Fragments from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="97c5c-118">Показывает, как организовать поток XML-фрагментов с помощью <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="97c5c-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="97c5c-119">При обработке объемных XML-файлов может оказаться, что загрузка в память всего дерева XML неосуществима.</span><span class="sxs-lookup"><span data-stu-id="97c5c-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="97c5c-120">Вместо этого можно организовать поток XML-фрагментов.</span><span class="sxs-lookup"><span data-stu-id="97c5c-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97c5c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="97c5c-121">See also</span></span>

- [<span data-ttu-id="97c5c-122">Создание деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="97c5c-122">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
