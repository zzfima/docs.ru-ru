---
title: "Сериализация XML и SOAP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 006727e70c58834a4e628f584a28302a62363844
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="6f7bc-102">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="6f7bc-102">XML and SOAP Serialization</span></span>
<span data-ttu-id="6f7bc-103">При сериализации XML открытые поля и свойства объекта или параметры и возвращаемые значения методов преобразуются (сериализуются) в поток XML в соответствии со специальным документом, составленном на языке XSD (язык определения схемы XML).</span><span class="sxs-lookup"><span data-stu-id="6f7bc-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="6f7bc-104">XML-сериализация приводит к образованию строго типизированных классов с открытыми свойствами и полями, которые преобразуются в серийный формат (в данном случае - XML) для хранения и передачи.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>  
  
 <span data-ttu-id="6f7bc-105">Поскольку стандарт XML является открытым, поток XML может обработать любое необходимое приложение независимо от платформы.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="6f7bc-106">Например, XML-веб-службы, созданные с помощью ASP.NET, используют класс <xref:System.Xml.Serialization.XmlSerializer>, чтобы создавать потоки XML, которые передают данные между приложениями веб-службы XML через Интернет или интрасети.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="6f7bc-107">И наоборот, при десериализации используется такой поток и воссоздается объект.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>  
  
 <span data-ttu-id="6f7bc-108">XML-сериализация может также использоваться для сериализации объектов в потоки XML, которые соответствуют спецификации SOAP.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="6f7bc-109">SOAP - это протокол, основанный на XML и созданный специально для передачи вызовов процедур с использованием XML.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>  
  
 <span data-ttu-id="6f7bc-110">Чтобы сериализовать и десериализовать объекты, используйте класс <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="6f7bc-111">Чтобы создать классы для их последующей сериализации, используйте инструмент определения схемы XML.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f7bc-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6f7bc-112">In This Section</span></span>  
 [<span data-ttu-id="6f7bc-113">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-113">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 <span data-ttu-id="6f7bc-114">Содержит общее определение сериализации, в особенности, XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-114">Provides a general definition of serialization, particularly XML serialization.</span></span>  
  
 [<span data-ttu-id="6f7bc-115">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="6f7bc-115">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 <span data-ttu-id="6f7bc-116">Содержит пошаговые инструкции по сериализации объекта.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-116">Provides step-by-step instructions for serializing an object.</span></span>  
  
 [<span data-ttu-id="6f7bc-117">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="6f7bc-117">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 <span data-ttu-id="6f7bc-118">Содержит пошаговые инструкции по десериализации объекта.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-118">Provides step-by-step instructions for deserializing an object.</span></span>  
  
 [<span data-ttu-id="6f7bc-119">Примеры сериализации XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-119">Examples of XML Serialization</span></span>](../../../docs/standard/serialization/examples-of-xml-serialization.md)  
 <span data-ttu-id="6f7bc-120">Содержит примеры, демонстрирующие основные возможности XML-сериализации .</span><span class="sxs-lookup"><span data-stu-id="6f7bc-120">Provides examples that demonstrate the basics of XML serialization.</span></span>  
  
 [<span data-ttu-id="6f7bc-121">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-121">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 <span data-ttu-id="6f7bc-122">Содержит описание правил использования инструмента определения схемы XML для создания классов, которые соответствуют определенной схеме языка определения схемы XML (XSD), или создания схемы XML из файла DLL.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>  
  
 [<span data-ttu-id="6f7bc-123">Управление сериализацией XML с использованием атрибутов</span><span class="sxs-lookup"><span data-stu-id="6f7bc-123">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 <span data-ttu-id="6f7bc-124">Содержит описание, как управлять сериализацией с помощью атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-124">Describes how to control serialization by using attributes.</span></span>  
  
 [<span data-ttu-id="6f7bc-125">Атрибуты управления сериализацией XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 <span data-ttu-id="6f7bc-126">Содержит список атрибутов, используемых для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-126">Lists the attributes that are used to control XML serialization.</span></span>  
  
 [<span data-ttu-id="6f7bc-127">Практическое руководство. Указание имени альтернативного элемента для потока XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 <span data-ttu-id="6f7bc-128">Содержит сложный сценарий, в котором описывается, как создавать несколько потоков XML путем переопределения сериализации.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>  
  
 [<span data-ttu-id="6f7bc-129">Практическое руководство. Управление сериализацией производных классов</span><span class="sxs-lookup"><span data-stu-id="6f7bc-129">How to: Control Serialization of Derived Classes</span></span>](../../../docs/standard/serialization/how-to-control-serialization-of-derived-classes.md)  
 <span data-ttu-id="6f7bc-130">Содержит пример, в котором показан способ управления сериализацией производных классов.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-130">Provides an example of how to control the serialization of derived classes.</span></span>  
  
 [<span data-ttu-id="6f7bc-131">Практическое руководство. Квалификация элемента XML и имен атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-131">How to: Qualify XML Element and XML Attribute Names</span></span>](../../../docs/standard/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 <span data-ttu-id="6f7bc-132">Содержит описание, как определять и управлять способом, с помощью которого в потоке XML используются пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>  
  
 [<span data-ttu-id="6f7bc-133">Сериализация XML с использованием XML-веб-служб</span><span class="sxs-lookup"><span data-stu-id="6f7bc-133">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 <span data-ttu-id="6f7bc-134">Содержит объяснение способов использования XML-сериализации в веб-службах XML.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-134">Explains how XML serialization is used in XML Web services.</span></span>  
  
 [<span data-ttu-id="6f7bc-135">Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="6f7bc-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 <span data-ttu-id="6f7bc-136">Содержит описание, как использовать класс <xref:System.Xml.Serialization.XmlSerializer> для создания потоков XML с кодировкой SOAP, соответствующих разделу 5 документа "Simple Object Access Protocol (SOAP) 1.1" консорциума World Wide Web Consortium (www.w3.org).</span><span class="sxs-lookup"><span data-stu-id="6f7bc-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (www.w3.org) document titled "Simple Object Access Protocol (SOAP) 1.1."</span></span>  
  
 [<span data-ttu-id="6f7bc-137">Практическое руководство. Переопределение сериализации XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="6f7bc-137">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 <span data-ttu-id="6f7bc-138">Содержит описание процесса переопределения XML-сериализации объектов как сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>  
  
 [<span data-ttu-id="6f7bc-139">Атрибуты управления сериализацией с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="6f7bc-139">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 <span data-ttu-id="6f7bc-140">Содержит список атрибутов, используемых для управления сериализацией с кодировкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>  
  
 [<span data-ttu-id="6f7bc-141">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="6f7bc-141">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 <span data-ttu-id="6f7bc-142">Элемент конфигурации верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-142">The top-level configuration element for controlling XML serialization.</span></span>  
  
 [<span data-ttu-id="6f7bc-143">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="6f7bc-143">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 <span data-ttu-id="6f7bc-144">Содержит информацию об управлении режимом сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 [<span data-ttu-id="6f7bc-145">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6f7bc-145">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 <span data-ttu-id="6f7bc-146">Содержит типы, используемые классом <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>  
  
 [<span data-ttu-id="6f7bc-147">Элемент \<add> для элемента \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6f7bc-147">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 <span data-ttu-id="6f7bc-148">Добавляет типы, используемые классом <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f7bc-149">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6f7bc-149">Related Sections</span></span>  
 [<span data-ttu-id="6f7bc-150">Расширенные технологии разработки</span><span class="sxs-lookup"><span data-stu-id="6f7bc-150">Advanced Development Technologies</span></span>](http://msdn.microsoft.com/en-us/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 <span data-ttu-id="6f7bc-151">Содержит ссылки на дополнительные сведения о сложных задачах и методиках разработки приложений в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-151">Provides links to more information on sophisticated development tasks and techniques in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="6f7bc-152">Веб-службы XML, созданные с помощью ASP.NET, и клиенты веб-служб с поддержкой XML</span><span class="sxs-lookup"><span data-stu-id="6f7bc-152">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 <span data-ttu-id="6f7bc-153">Содержит разделы с описаниями и объяснением программирования XML-веб-служб с помощью ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6f7bc-153">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7bc-154">См. также</span><span class="sxs-lookup"><span data-stu-id="6f7bc-154">See Also</span></span>  
 [<span data-ttu-id="6f7bc-155">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="6f7bc-155">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
