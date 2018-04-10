---
title: XML-документы и данные
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 824e06a00c4242d8ee38bdfc5a57151a71e4f285
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2018
---
# <a name="xml-documents-and-data"></a><span data-ttu-id="88ead-102">XML-документы и данные</span><span class="sxs-lookup"><span data-stu-id="88ead-102">XML Documents and Data</span></span>
<span data-ttu-id="88ead-103">Платформа .NET Framework имеет всеобъемлющий и интегрированный набор классов, с помощью которых можно легко создавать приложения, использующие XML.</span><span class="sxs-lookup"><span data-stu-id="88ead-103">The .NET Framework provides a comprehensive and integrated set of classes that enable you to build XML-aware apps easily.</span></span> <span data-ttu-id="88ead-104">Классы из следующих пространств имен поддерживают синтаксический анализ и запись XML-кода, изменение XML-данных в памяти, проверку данных и преобразование XSLT.</span><span class="sxs-lookup"><span data-stu-id="88ead-104">The classes in the following namespaces support parsing and writing XML, editing XML data in memory, data validation, and XSLT transformation.</span></span>  
  
-   <xref:System.Xml>  
  
-   <xref:System.Xml.XPath>  
  
-   <xref:System.Xml.Xsl>  
  
-   <xref:System.Xml.Schema>  
  
-   <xref:System.Xml.Linq>  
  
 <span data-ttu-id="88ead-105">Полный список приведен на странице [Пространства имен System.Xml](http://msdn.microsoft.com/library/gg145036.aspx).</span><span class="sxs-lookup"><span data-stu-id="88ead-105">For a full list, see the [System.Xml Namespaces](http://msdn.microsoft.com/library/gg145036.aspx) webpage.</span></span>  
  
 <span data-ttu-id="88ead-106">Классы из этих пространств имен поддерживают рекомендации W3C.</span><span class="sxs-lookup"><span data-stu-id="88ead-106">The classes in these namespaces support World Wide Web Consortium (W3C) recommendations.</span></span> <span data-ttu-id="88ead-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="88ead-107">For example:</span></span>  
  
-   <span data-ttu-id="88ead-108">Класс <xref:System.Xml.XmlDocument?displayProperty=nameWithType> реализует рекомендации модели W3C [DOM базового уровня 1](http://www.w3.org/TR/REC-DOM-Level-1/) и [DOM базового уровня 2](http://www.w3.org/TR/DOM-Level-2-Core/).</span><span class="sxs-lookup"><span data-stu-id="88ead-108">The <xref:System.Xml.XmlDocument?displayProperty=nameWithType> class implements the [W3C Document Object Model (DOM) Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/) and [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) recommendations.</span></span>  
  
-   <span data-ttu-id="88ead-109">Классы <xref:System.Xml.XmlReader?displayProperty=nameWithType> и <xref:System.Xml.XmlWriter?displayProperty=nameWithType> поддерживают рекомендации [W3C XML 1.0](http://www.w3.org/TR/2006/REC-xml-20060816/) и [Пространства имен в XML](http://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="88ead-109">The <xref:System.Xml.XmlReader?displayProperty=nameWithType> and <xref:System.Xml.XmlWriter?displayProperty=nameWithType> classes support the [W3C XML 1.0](http://www.w3.org/TR/2006/REC-xml-20060816/) and the [Namespaces in XML](http://www.w3.org/TR/REC-xml-names/) recommendations.</span></span>  
  
-   <span data-ttu-id="88ead-110">Схемы из класса <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> поддерживают рекомендации W3C [Схема XML. Часть 1. Структуры](http://www.w3.org/TR/xmlschema-1/) и [Схема XML. Часть 2. Типы данных](http://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="88ead-110">Schemas in the <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> class support the [W3C XML Schema Part 1: Structures](http://www.w3.org/TR/xmlschema-1/) and [XML Schema Part 2: Datatypes](http://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>  
  
-   <span data-ttu-id="88ead-111">Классы в пространстве имен <xref:System.Xml.Xsl?displayProperty=nameWithType> поддерживают преобразования XSLT, соответствующие рекомендациям [W3C XSLT 1.0](http://www.w3.org/TR/xslt).</span><span class="sxs-lookup"><span data-stu-id="88ead-111">Classes in the <xref:System.Xml.Xsl?displayProperty=nameWithType> namespace support XSLT transformations that conform to the [W3C XSLT 1.0](http://www.w3.org/TR/xslt) recommendation.</span></span>  
  
 <span data-ttu-id="88ead-112">Классы XML в платформе .NET Framework предоставляют следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="88ead-112">The XML classes in the .NET Framework provide these benefits:</span></span>  
  
-   <span data-ttu-id="88ead-113">**Производительность**</span><span class="sxs-lookup"><span data-stu-id="88ead-113">**Productivity.**</span></span> <span data-ttu-id="88ead-114">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) упрощает программирование с использованием XML и обеспечивает работу с запросами, похожую на работу в SQL.</span><span class="sxs-lookup"><span data-stu-id="88ead-114">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) makes it easier to program with XML and provides a query experience that is similar to SQL.</span></span>  
  
-   <span data-ttu-id="88ead-115">**Расширяемость**</span><span class="sxs-lookup"><span data-stu-id="88ead-115">**Extensibility.**</span></span> <span data-ttu-id="88ead-116">XML-классы в .NET Framework являются расширяемыми, что было достигнуто за счет использования абстрактных базовых классов и виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="88ead-116">The XML classes in the .NET Framework are extensible through the use of abstract base classes and virtual methods.</span></span> <span data-ttu-id="88ead-117">Например, можно создать класс, производный от класса <xref:System.Xml.XmlUrlResolver>, который будет сохранять поток кэширования на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="88ead-117">For example, you can create a derived class of the <xref:System.Xml.XmlUrlResolver> class that stores the cache stream to the local disk.</span></span>  
  
-   <span data-ttu-id="88ead-118">**Модульная архитектура**</span><span class="sxs-lookup"><span data-stu-id="88ead-118">**Pluggable architecture.**</span></span> <span data-ttu-id="88ead-119">Платформа .NET Framework обеспечивает архитектуру, в которой компоненты могут использовать друг друга, а данные можно передавать в потоках между компонентами.</span><span class="sxs-lookup"><span data-stu-id="88ead-119">The .NET Framework provides an architecture in which components can utilize one another, and data can be streamed between components.</span></span> <span data-ttu-id="88ead-120">Например, хранилище данных, такое как объект <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>, можно преобразовать с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>, а выходные данные затем могут быть переданы в виде потока в другое хранилище или возвращены в виде потока из веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="88ead-120">For example, a data store, such as an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, can be transformed with the <xref:System.Xml.Xsl.XslCompiledTransform> class, and the output can then be streamed either into another store or returned as a stream from a web service.</span></span>  
  
-   <span data-ttu-id="88ead-121">**Производительность.**</span><span class="sxs-lookup"><span data-stu-id="88ead-121">**Performance.**</span></span> <span data-ttu-id="88ead-122">С целью повышения быстродействия приложений некоторые XML-классы в .NET Framework поддерживают модель на основе потоковой передачи со следующими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="88ead-122">For better app performance, some of the XML classes in the .NET Framework support a streaming-based model with the following characteristics:</span></span>  
  
    -   <span data-ttu-id="88ead-123">Минимальное кэширование для анализа по запросу в однопроходном режиме (<xref:System.Xml.XmlReader>).</span><span class="sxs-lookup"><span data-stu-id="88ead-123">Minimal caching for forward-only, pull-model parsing (<xref:System.Xml.XmlReader>).</span></span>  
  
    -   <span data-ttu-id="88ead-124">Проверка в однопроходном режиме (<xref:System.Xml.XmlReader>).</span><span class="sxs-lookup"><span data-stu-id="88ead-124">Forward-only validation (<xref:System.Xml.XmlReader>).</span></span>  
  
    -   <span data-ttu-id="88ead-125">Навигация, аналогичная курсорам, которая сводит создание узлов к минимуму (до одного виртуального узла) и обеспечивает произвольный доступ к документу (<xref:System.Xml.XPath.XPathNavigator>).</span><span class="sxs-lookup"><span data-stu-id="88ead-125">Cursor style navigation that minimizes node creation to a single virtual node while providing random access to the document (<xref:System.Xml.XPath.XPathNavigator>).</span></span>  
  
     <span data-ttu-id="88ead-126">В случае если требуется обработка XSLT, для повышения производительности можно использовать класс <xref:System.Xml.XPath.XPathDocument>, который является оптимизированным хранилищем «только для чтения» для запросов XPath, обеспечивающих эффективное взаимодействие с классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="88ead-126">For better performance whenever XSLT processing is required, you can use the <xref:System.Xml.XPath.XPathDocument> class, which is an optimized, read-only store for XPath queries designed to work efficiently with the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
-   <span data-ttu-id="88ead-127">**Интеграция с ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="88ead-127">**Integration with ADO.NET.**</span></span> <span data-ttu-id="88ead-128">Классы XML и [ADO.NET](../../../../docs/framework/data/adonet/index.md) тесно интегрированы для сведения воедино реляционных данных и XML.</span><span class="sxs-lookup"><span data-stu-id="88ead-128">The XML classes and [ADO.NET](../../../../docs/framework/data/adonet/index.md) are tightly integrated to bring together relational data and XML.</span></span> <span data-ttu-id="88ead-129">Класс <xref:System.Data.DataSet> представляет собой кэш «в памяти» для данных, полученных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="88ead-129">The <xref:System.Data.DataSet> class is an in-memory cache of data retrieved from a database.</span></span> <span data-ttu-id="88ead-130">Класс <xref:System.Data.DataSet> позволяет считывать и записывать код XML с помощью классов <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>, сохранять внутреннюю реляционную структуру в виде схем XML (XSD) и логически выводить структуру схем XML-документов.</span><span class="sxs-lookup"><span data-stu-id="88ead-130">The <xref:System.Data.DataSet> class has the ability to read and write XML by using the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> classes, to persist its internal relational schema structure as XML schemas (XSD), and to infer the schema structure of an XML document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88ead-131">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="88ead-131">In This Section</span></span>  
 [<span data-ttu-id="88ead-132">Параметры обработки XML</span><span class="sxs-lookup"><span data-stu-id="88ead-132">XML Processing Options</span></span>](../../../../docs/standard/data/xml/xml-processing-options.md)  
 <span data-ttu-id="88ead-133">Обсуждаются параметры обработки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="88ead-133">Discusses options for processing XML data.</span></span>  
  
 [<span data-ttu-id="88ead-134">Обработка XML-данных в памяти</span><span class="sxs-lookup"><span data-stu-id="88ead-134">Processing XML Data In-Memory</span></span>](../../../../docs/standard/data/xml/processing-xml-data-in-memory.md)  
 <span data-ttu-id="88ead-135">Содержит обсуждение трех моделей обработки XML-данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="88ead-135">Discusses the three models for processing XML data in-memory.</span></span> <span data-ttu-id="88ead-136">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13), класс <xref:System.Xml.XmlDocument> (основанный на модели W3C DOM) и класс <xref:System.Xml.XPath.XPathDocument> (основанный на модели данных XPath).</span><span class="sxs-lookup"><span data-stu-id="88ead-136">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13), the <xref:System.Xml.XmlDocument> class (based on the W3C Document Object Model), and the <xref:System.Xml.XPath.XPathDocument> class (based on the XPath data model).</span></span>  
  
 [<span data-ttu-id="88ead-137">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="88ead-137">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 <span data-ttu-id="88ead-138">Описывается, как использовать обработчик XSLT.</span><span class="sxs-lookup"><span data-stu-id="88ead-138">Describes how to use the XSLT processor.</span></span>  
  
 [<span data-ttu-id="88ead-139">Модель объектов схемы XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="88ead-139">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="88ead-140">Описываются классы, используемые для построения схем XML (XSD-файлов) и работы с ними, используя класс <xref:System.Xml.Schema.XmlSchema> для загрузки и изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="88ead-140">Describes the classes used for building and manipulating XML Schemas (XSD) by providing an <xref:System.Xml.Schema.XmlSchema> class to load and edit a schema.</span></span>  
  
 [<span data-ttu-id="88ead-141">Интеграция XML с реляционными данными и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88ead-141">XML Integration with Relational Data and ADO.NET</span></span>](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)  
 <span data-ttu-id="88ead-142">Описывается, как платформа .NET Framework реализует синхронный доступ в режиме реального времени к данным в реляционном и иерархическом представлении с помощью объектов <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="88ead-142">Describes how the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the <xref:System.Data.DataSet> object and the <xref:System.Xml.XmlDataDocument> object.</span></span>  
  
 [<span data-ttu-id="88ead-143">Управление пространствами имен в XML-документе</span><span class="sxs-lookup"><span data-stu-id="88ead-143">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)  
 <span data-ttu-id="88ead-144">Описывает использование класса <xref:System.Xml.XmlNamespaceManager> для хранения и ведения информации о пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="88ead-144">Describes how the <xref:System.Xml.XmlNamespaceManager> class is used to store and maintain namespace information.</span></span>  
  
 [<span data-ttu-id="88ead-145">Поддержка типов в классах System.Xml</span><span class="sxs-lookup"><span data-stu-id="88ead-145">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)  
 <span data-ttu-id="88ead-146">Описывает сопоставление типов данных XML с типами CLR, преобразование типов данных XML и другие функции по работе с типами, которые есть в классах <xref:System.Xml>.</span><span class="sxs-lookup"><span data-stu-id="88ead-146">Describes how XML data types map to CLR types, how to convert XML data types, and other type support features in the <xref:System.Xml> classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="88ead-147">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="88ead-147">Related Sections</span></span>  
 [<span data-ttu-id="88ead-148">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88ead-148">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="88ead-149">Приводятся сведения о доступе к данным с помощью ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="88ead-149">Provides information on how to access data using ADO.NET.</span></span>  
  
 [<span data-ttu-id="88ead-150">Безопасность</span><span class="sxs-lookup"><span data-stu-id="88ead-150">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="88ead-151">Приводятся общие сведения о системе безопасности в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88ead-151">Provides an overview of the .NET Framework security system.</span></span>  
  