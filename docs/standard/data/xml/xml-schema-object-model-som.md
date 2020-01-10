---
title: Модель объектов схемы XML (SOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a897a599-ffd1-43f9-8807-e58c8a7194cd
ms.openlocfilehash: 45bfba7bdab31b3edda59a350788e50182123ce0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709911"
---
# <a name="xml-schema-object-model-som"></a><span data-ttu-id="bec40-102">Модель объектов схемы XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="bec40-102">XML Schema Object Model (SOM)</span></span>
<span data-ttu-id="bec40-103">Схема XML - это мощное и сложное средство создания и проверки структуры в совместимых XML-документах.</span><span class="sxs-lookup"><span data-stu-id="bec40-103">An XML schema is a powerful and complex tool for creating and validating structure in compliant XML documents.</span></span> <span data-ttu-id="bec40-104">Схема, так же как и моделирование данных в реляционной базе данных, позволяет определять структуру XML-документов путем указания элементов, которые могут использоваться в документах, а также структуры и типов, которых эти элементы должны придерживаться, чтобы быть допустимыми с точки зрения этой конкретной схемы.</span><span class="sxs-lookup"><span data-stu-id="bec40-104">Similar to data modeling in a relational database, a schema provides a way to define the structure of XML documents, by specifying the elements that can be used in the documents, as well as the structure and types that these elements must follow in order to be valid for that specific schema.</span></span>  
  
 <span data-ttu-id="bec40-105">Модель SOM предоставляет набор классов в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, которые позволяют считывать схему из файла или программно создавать схему в памяти.</span><span class="sxs-lookup"><span data-stu-id="bec40-105">The Schema Object Model (SOM) provides a set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that allow you to read a schema from a file or to programmatically create a schema in-memory.</span></span> <span data-ttu-id="bec40-106">После этого схему можно будет просматривать, изменять, компилировать, проверять или записывать в файл.</span><span class="sxs-lookup"><span data-stu-id="bec40-106">The schema can then be traversed, editing, compiled, validated, or written to a file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bec40-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bec40-107">In This Section</span></span>  
 [<span data-ttu-id="bec40-108">Общие сведения об модели объектов XML-схемы</span><span class="sxs-lookup"><span data-stu-id="bec40-108">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 <span data-ttu-id="bec40-109">Описывает модель SOM и ее возможности и классы.</span><span class="sxs-lookup"><span data-stu-id="bec40-109">Describes the Schema Object Model (SOM) and the features and classes it provides.</span></span>  
  
 [<span data-ttu-id="bec40-110">Чтение и запись XML-схем</span><span class="sxs-lookup"><span data-stu-id="bec40-110">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 <span data-ttu-id="bec40-111">Описывает, как считывать и записывать схемы XML из файлов или других ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bec40-111">Describes how to read and write XML schemas from files or other sources.</span></span>  
  
 [<span data-ttu-id="bec40-112">Построение XML-схем</span><span class="sxs-lookup"><span data-stu-id="bec40-112">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 <span data-ttu-id="bec40-113">Описывает, как использовать классы в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, чтобы строить схемы XML в памяти.</span><span class="sxs-lookup"><span data-stu-id="bec40-113">Describes how to use the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace to build XML schemas in-memory.</span></span>  
  
 [<span data-ttu-id="bec40-114">Обход XML-схем</span><span class="sxs-lookup"><span data-stu-id="bec40-114">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 <span data-ttu-id="bec40-115">Описывает, как просматривать схему XML, чтобы получить доступ к элементам, атрибутам и типам, хранящимся в модели SOM.</span><span class="sxs-lookup"><span data-stu-id="bec40-115">Describes how to traverse an XML schema to access the elements, attributes, and types stored in the SOM.</span></span>  
  
 [<span data-ttu-id="bec40-116">Изменение XML-схем</span><span class="sxs-lookup"><span data-stu-id="bec40-116">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 <span data-ttu-id="bec40-117">Описывает, как изменять схемы XML.</span><span class="sxs-lookup"><span data-stu-id="bec40-117">Describes how to edit an XML schema.</span></span>  
  
 [<span data-ttu-id="bec40-118">Включение или импорт XML-схем</span><span class="sxs-lookup"><span data-stu-id="bec40-118">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 <span data-ttu-id="bec40-119">Описывает, как включать или импортировать другие схемы XML, чтобы дополнять структуру схемы, в которую они включаются или импортируются.</span><span class="sxs-lookup"><span data-stu-id="bec40-119">Describes how to include or import other XML schemas to supplement the structure of the schema that includes or imports them.</span></span>
