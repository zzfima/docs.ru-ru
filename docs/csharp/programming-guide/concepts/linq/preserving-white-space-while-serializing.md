---
title: "Сохранение пробелов при сериализации3"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eed3f2a2627fb5901692d67095efbdd5c874b54c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="e0395-102">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="e0395-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="e0395-103">В этом разделе описывается управление пробелами при сериализации XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="e0395-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="e0395-104">Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами.</span><span class="sxs-lookup"><span data-stu-id="e0395-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="e0395-105">При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="e0395-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="e0395-106">Это поведение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0395-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="e0395-107">Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами.</span><span class="sxs-lookup"><span data-stu-id="e0395-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="e0395-108">Эти отступы ни в коем случае изменять нельзя.</span><span class="sxs-lookup"><span data-stu-id="e0395-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="e0395-109">Для этого в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="e0395-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="e0395-110">Управление пробелами в методах сериализации XML-деревьев</span><span class="sxs-lookup"><span data-stu-id="e0395-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="e0395-111">Следующие методы классов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument> позволяют сериализовать XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="e0395-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="e0395-112">Можно сериализовать XML-дерево в файл, объект <xref:System.IO.TextReader> или объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="e0395-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="e0395-113">Метод `ToString` позволяет сериализовать в строку.</span><span class="sxs-lookup"><span data-stu-id="e0395-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName>  
  
 <span data-ttu-id="e0395-114">Если метод не берет объект <xref:System.Xml.Linq.SaveOptions> в качестве аргумента, то этот метод отформатирует (расставит отступы) сериализованный XML.</span><span class="sxs-lookup"><span data-stu-id="e0395-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="e0395-115">В этом случае все незначащие пробелы в XML-дереве удаляются.</span><span class="sxs-lookup"><span data-stu-id="e0395-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="e0395-116">Если метод берет объект <xref:System.Xml.Linq.SaveOptions> в качестве аргумента, то можно указать, что этот метод не должен форматировать (расставлять отступы) сериализованный XML.</span><span class="sxs-lookup"><span data-stu-id="e0395-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="e0395-117">В этом случае все незначащие пробелы в XML-дереве сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e0395-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0395-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e0395-118">See Also</span></span>  
 [<span data-ttu-id="e0395-119">Сериализация XML-деревьев (C#)</span><span class="sxs-lookup"><span data-stu-id="e0395-119">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

