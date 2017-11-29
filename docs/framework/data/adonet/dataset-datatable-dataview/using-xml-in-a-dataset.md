---
title: "Использование XML в наборах данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28c1668dcb9678b65db62c0040adcd116221b92e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="15f7e-102">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="15f7e-102">Using XML in a DataSet</span></span>
<span data-ttu-id="15f7e-103">В ADO.NET можно заполнить <xref:System.Data.DataSet> из XML-потока или документа.</span><span class="sxs-lookup"><span data-stu-id="15f7e-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="15f7e-104">XML-поток или XML-документ можно использовать для предоставления объекту <xref:System.Data.DataSet> данных, информации о схеме или того и другого.</span><span class="sxs-lookup"><span data-stu-id="15f7e-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="15f7e-105">Данные из XML-потока или документа можно комбинировать с существующими в <xref:System.Data.DataSet> данными или сведениями о схеме.</span><span class="sxs-lookup"><span data-stu-id="15f7e-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="15f7e-106">ADO.NET также позволяет создавать XML-представление <xref:System.Data.DataSet> с его схемой или без нее с целью передать <xref:System.Data.DataSet> по HTTP для использования в другом приложении или на платформе, поддерживающей XML.</span><span class="sxs-lookup"><span data-stu-id="15f7e-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="15f7e-107">В XML-представлении набора данных <xref:System.Data.DataSet> данные записываются на языке XML, а схема, если она встроена в представление, записывается на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="15f7e-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="15f7e-108">XML и схема XML предоставляют удобный формат для передачи содержимого объекта <xref:System.Data.DataSet> удаленному клиенту и обратно.</span><span class="sxs-lookup"><span data-stu-id="15f7e-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15f7e-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="15f7e-109">In This Section</span></span>  
 [<span data-ttu-id="15f7e-110">Дельты</span><span class="sxs-lookup"><span data-stu-id="15f7e-110">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 <span data-ttu-id="15f7e-111">Содержит подробные сведения о DiffGram, XML-формате, который используется для чтения и записи содержимого класса <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="15f7e-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="15f7e-112">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="15f7e-112">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 <span data-ttu-id="15f7e-113">Объясняет различные параметры, которые следует учитывать при загрузке содержимого класса <xref:System.Data.DataSet> из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="15f7e-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="15f7e-114">Запись содержимого набора как XML-данных</span><span class="sxs-lookup"><span data-stu-id="15f7e-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="15f7e-115">Объясняет способы создания содержимого класса <xref:System.Data.DataSet> в виде XML-данных и различные доступные параметры XML-формата.</span><span class="sxs-lookup"><span data-stu-id="15f7e-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="15f7e-116">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="15f7e-116">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="15f7e-117">Объясняет методы класса <xref:System.Data.DataSet>, которые используются для загрузки схемы <xref:System.Data.DataSet> из XML.</span><span class="sxs-lookup"><span data-stu-id="15f7e-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="15f7e-118">Запись сведений о схеме набора данных как XSD</span><span class="sxs-lookup"><span data-stu-id="15f7e-118">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="15f7e-119">Объясняет использование схемы XML и ее создание из класса <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="15f7e-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="15f7e-120">Набор данных и XmlDataDocument синхронизации</span><span class="sxs-lookup"><span data-stu-id="15f7e-120">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="15f7e-121">Объясняет доступные в .NET Framework возможности синхронного доступа как к реляционным, так и иерархическим представлениям одного набора данных, а также демонстрирует создание синхронных связей между <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="15f7e-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="15f7e-122">Вложение отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="15f7e-122">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="15f7e-123">Объясняет значение вложенных объектов <xref:System.Data.DataRelation> при представлении содержимого класса <xref:System.Data.DataSet> как XML-данных и описывает создание этих объектов.</span><span class="sxs-lookup"><span data-stu-id="15f7e-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="15f7e-124">Наследование реляционной структуры набора данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="15f7e-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="15f7e-125">Объясняет реляционную структуру (схему) класса <xref:System.Data.DataSet>, созданную из схемы XML.</span><span class="sxs-lookup"><span data-stu-id="15f7e-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="15f7e-126">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="15f7e-126">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="15f7e-127">Объясняет полученную реляционную структуру (или схему) класса <xref:System.Data.DataSet>, созданную при использовании XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="15f7e-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="15f7e-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="15f7e-128">Related Sections</span></span>  
 [<span data-ttu-id="15f7e-129">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="15f7e-129">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="15f7e-130">Описывает архитектуру и компоненты ADO.NET, а также способы их использования для доступа к существующим источникам данных и управления данными приложения.</span><span class="sxs-lookup"><span data-stu-id="15f7e-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f7e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="15f7e-131">See Also</span></span>  
 [<span data-ttu-id="15f7e-132">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="15f7e-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="15f7e-133">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="15f7e-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
