---
title: "Синтаксический анализ XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bcbd7e2-d9f1-4c8f-80d6-39915fe17bd1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6eed674ff6168690e627abf8c5c13665c07c35aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-xml-visual-basic"></a><span data-ttu-id="621e3-102">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-102">Parsing XML (Visual Basic)</span></span>
<span data-ttu-id="621e3-103">Подразделы в данном разделе описывают синтаксический анализ XML-документов.</span><span class="sxs-lookup"><span data-stu-id="621e3-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="621e3-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="621e3-104">In This Section</span></span>  
  
|<span data-ttu-id="621e3-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="621e3-105">Topic</span></span>|<span data-ttu-id="621e3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="621e3-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="621e3-107">Как: синтаксический анализ строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-107">How to: Parse a String (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="621e3-108">Показывает, как анализировать строку для создания XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="621e3-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="621e3-109">Как: загрузить XML из файла (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-109">How to: Load XML from a File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="621e3-110">Показывает, как загружать XML из URI-кода с помощью метода <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="621e3-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="621e3-111">Сохранение пробелов при загрузке и анализе XML</span><span class="sxs-lookup"><span data-stu-id="621e3-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml.md)|<span data-ttu-id="621e3-112">Описывает, как управлять поведением пробелов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] при загрузке XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="621e3-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="621e3-113">Как: перехватывать синтаксический анализ ошибок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-113">How to: Catch Parsing Errors (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="621e3-114">Показывает, как выявлять плохо отформатированные или недопустимые коды XML.</span><span class="sxs-lookup"><span data-stu-id="621e3-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="621e3-115">Как: Создание дерева из XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-115">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="621e3-116">Показывает, как создавать XML-дерево непосредственно из <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="621e3-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="621e3-117">Как: потоковая передача фрагментов XML из XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-117">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="621e3-118">Показывает, как организовать поток XML-фрагментов с помощью <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="621e3-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="621e3-119">При обработке объемных XML-файлов может оказаться, что загрузка в память всего дерева XML неосуществима.</span><span class="sxs-lookup"><span data-stu-id="621e3-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="621e3-120">Вместо этого можно организовать поток XML-фрагментов.</span><span class="sxs-lookup"><span data-stu-id="621e3-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="621e3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="621e3-121">See Also</span></span>  
 [<span data-ttu-id="621e3-122">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621e3-122">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
