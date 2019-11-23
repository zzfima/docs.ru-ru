---
title: 'How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 9b2cd67a1c4f30e6fe246124be5b8f7081c539a6
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392861"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="49a72-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span><span class="sxs-lookup"><span data-stu-id="49a72-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="49a72-103">С помощью инструмента определения схемы XML (Xsd.exe) можно создать схему XML, которая описывает класс, или создать класс, определенный схемой XML.</span><span class="sxs-lookup"><span data-stu-id="49a72-103">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="49a72-104">В процедурах ниже показана методика выполнения таких операций.</span><span class="sxs-lookup"><span data-stu-id="49a72-104">The following procedures show how to perform these operations.</span></span>  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="49a72-105">Создание классов, соответствующих определенной схеме</span><span class="sxs-lookup"><span data-stu-id="49a72-105">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="49a72-106">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="49a72-106">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="49a72-107">Передайте схему XML как аргумент в инструмент определения схемы XML, который создаст набор классов, точно соответствующих схеме XML, например:</span><span class="sxs-lookup"><span data-stu-id="49a72-107">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="49a72-108">Средство может обрабатывать только схемы, которые ссылаются на спецификацию XML консорциума W3C от 16 марта 2001 г.</span><span class="sxs-lookup"><span data-stu-id="49a72-108">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="49a72-109">Иными словами, пространство имен XML-схемы должно иметь значение "http://www.w3.org/2001/XMLSchema", как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="49a72-109">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3. <span data-ttu-id="49a72-110">При необходимости измените классы с методами, свойствами или полями.</span><span class="sxs-lookup"><span data-stu-id="49a72-110">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="49a72-111">Дополнительные сведения об изменении класса с помощью атрибутов см. в разделах [Управление сериализацией XML с использованием атрибутов](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) и [Атрибуты управления сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="49a72-111">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="49a72-112">Часто бывает полезным изучить схему потока XML, которая генерируется при сериализации экземпляров класса (или классов).</span><span class="sxs-lookup"><span data-stu-id="49a72-112">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="49a72-113">Например, можно опубликовать схему для совместного использования или сравнить ее со схемой, в которой предпринимается попытка обеспечения соответствия.</span><span class="sxs-lookup"><span data-stu-id="49a72-113">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="49a72-114">Создание документа схемы XML из набора классов</span><span class="sxs-lookup"><span data-stu-id="49a72-114">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="49a72-115">Скомпилируйте класс или классы в библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="49a72-115">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="49a72-116">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="49a72-116">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="49a72-117">Передайте библиотеку DLL как аргумент в Xsd.exe, например:</span><span class="sxs-lookup"><span data-stu-id="49a72-117">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="49a72-118">В результате записывается схема (или схемы), которая начинается с имени "schema0.xsd".</span><span class="sxs-lookup"><span data-stu-id="49a72-118">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a72-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="49a72-119">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="49a72-120">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="49a72-120">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="49a72-121">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="49a72-121">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="49a72-122">Инструмент определения схемы XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="49a72-122">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="49a72-123">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="49a72-123">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="49a72-124">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="49a72-124">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
