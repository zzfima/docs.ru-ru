---
title: Анализ XML (C#)
ms.date: 07/20/2015
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
ms.openlocfilehash: a2dc3043c8cbf8138a164ab06d8394e4c859fa50
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523032"
---
# <a name="parsing-xml-c"></a><span data-ttu-id="eabb6-102">Анализ XML (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-102">Parsing XML (C#)</span></span>
<span data-ttu-id="eabb6-103">Подразделы в данном разделе описывают синтаксический анализ XML-документов.</span><span class="sxs-lookup"><span data-stu-id="eabb6-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eabb6-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="eabb6-104">In This Section</span></span>  
  
|<span data-ttu-id="eabb6-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="eabb6-105">Topic</span></span>|<span data-ttu-id="eabb6-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="eabb6-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="eabb6-107">Практическое руководство. Анализ строки (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-107">How to: Parse a String (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="eabb6-108">Показывает, как анализировать строку для создания XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="eabb6-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="eabb6-109">Практическое руководство. Загрузка XML-кода из файла (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-109">How to: Load XML from a File (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="eabb6-110">Показывает, как загружать XML из URI-кода с помощью метода <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="eabb6-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="eabb6-111">Сохранение пробелов при загрузке и анализе XML</span><span class="sxs-lookup"><span data-stu-id="eabb6-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="eabb6-112">Описывает, как управлять поведением пробелов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] при загрузке XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="eabb6-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="eabb6-113">Практическое руководство. Перехват ошибок анализа (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-113">How to: Catch Parsing Errors (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="eabb6-114">Показывает, как выявлять плохо отформатированные или недопустимые коды XML.</span><span class="sxs-lookup"><span data-stu-id="eabb6-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="eabb6-115">Практическое руководство. Создание дерева из XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-115">How to: Create a Tree from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="eabb6-116">Показывает, как создавать XML-дерево непосредственно из <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="eabb6-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="eabb6-117">Практическое руководство. Потоковая передача фрагментов XML из XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-117">How to: Stream XML Fragments from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="eabb6-118">Показывает, как организовать поток XML-фрагментов с помощью <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="eabb6-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="eabb6-119">При обработке объемных XML-файлов может оказаться, что загрузка в память всего дерева XML неосуществима.</span><span class="sxs-lookup"><span data-stu-id="eabb6-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="eabb6-120">Вместо этого можно организовать поток XML-фрагментов.</span><span class="sxs-lookup"><span data-stu-id="eabb6-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eabb6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="eabb6-121">See Also</span></span>

- [<span data-ttu-id="eabb6-122">Создание деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="eabb6-122">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
