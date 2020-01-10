---
title: Чтение и запись XML-схем
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 889c5f85a2ea3fc08dadefda5509de0fcfab76ec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710418"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="349f3-102">Чтение и запись XML-схем</span><span class="sxs-lookup"><span data-stu-id="349f3-102">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="349f3-103">API модели SOM можно использовать для чтения и записи схем на языке XSD из файлов или других источников, а также строить схемы XML в памяти с помощью классов в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, которые сопоставляются со структурами, определенными в рекомендациях W3C по схемам XML.</span><span class="sxs-lookup"><span data-stu-id="349f3-103">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="349f3-104">Чтение и запись XML-схем</span><span class="sxs-lookup"><span data-stu-id="349f3-104">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="349f3-105">Класс <xref:System.Xml.Schema.XmlSchema> предоставляет методы <xref:System.Xml.Schema.XmlSchema.Read%2A> и <xref:System.Xml.Schema.XmlSchema.Write%2A> для чтения и записи схем XML.</span><span class="sxs-lookup"><span data-stu-id="349f3-105">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="349f3-106">Метод <xref:System.Xml.Schema.XmlSchema.Read%2A> возвращает объект <xref:System.Xml.Schema.XmlSchema>, представляющий схему XML, и принимает необязательный объект <xref:System.Xml.Schema.ValidationEventHandler> в качестве параметра для обработки предупреждений и ошибок проверки схемы, обнаруженных при чтении схемы XML.</span><span class="sxs-lookup"><span data-stu-id="349f3-106">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="349f3-107">Метод <xref:System.Xml.Schema.XmlSchema.Write%2A> записывает схемы XML в объекты <xref:System.IO.Stream>, <xref:System.IO.TextWriter> и <xref:System.Xml.XmlWriter> и может принимать в качестве параметра необязательный объект <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="349f3-107">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="349f3-108">Объект <xref:System.Xml.XmlNamespaceManager> используется, чтобы обрабатывать пространства имен, обнаруженные в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="349f3-108">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="349f3-109">Дополнительные сведения о классе <xref:System.Xml.XmlNamespaceManager>см. в руководству по [пространствах имен в документе XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="349f3-109">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="349f3-110">Следующий пример кода иллюстрирует чтение из файла и запись в файл схем XML.</span><span class="sxs-lookup"><span data-stu-id="349f3-110">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="349f3-111">Пример кода берет файл `example.xsd`, считывает его в объект <xref:System.Xml.Schema.XmlSchema> с помощью метода `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>, а затем записывает файл в консоль и новый файл `new.xsd`.</span><span class="sxs-lookup"><span data-stu-id="349f3-111">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="349f3-112">Кроме того, в этом примере кода методу <xref:System.Xml.Schema.ValidationEventHandler>`static` в качестве параметра передается объект <xref:System.Xml.Schema.XmlSchema.Read%2A> для обработки любых предупреждений и ошибок проверки схемы, обнаруженных при чтении схемы XML.</span><span class="sxs-lookup"><span data-stu-id="349f3-112">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="349f3-113">Если объект <xref:System.Xml.Schema.ValidationEventHandler> не указан (значение `null`), об ошибках или предупреждениях сообщаться не будет.</span><span class="sxs-lookup"><span data-stu-id="349f3-113">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="349f3-114">В примере в качестве входных данных используется файл `example.xsd`.</span><span class="sxs-lookup"><span data-stu-id="349f3-114">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="349f3-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="349f3-115">See also</span></span>

- [<span data-ttu-id="349f3-116">Общие сведения об модели объектов XML-схемы</span><span class="sxs-lookup"><span data-stu-id="349f3-116">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="349f3-117">Построение XML-схем</span><span class="sxs-lookup"><span data-stu-id="349f3-117">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="349f3-118">Обход XML-схем</span><span class="sxs-lookup"><span data-stu-id="349f3-118">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="349f3-119">Изменение XML-схем</span><span class="sxs-lookup"><span data-stu-id="349f3-119">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="349f3-120">Включение или импорт XML-схем</span><span class="sxs-lookup"><span data-stu-id="349f3-120">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="349f3-121">XmlSchemaSet для компиляции схемы</span><span class="sxs-lookup"><span data-stu-id="349f3-121">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="349f3-122">Набор сведений для постсхемной компиляции</span><span class="sxs-lookup"><span data-stu-id="349f3-122">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
- [<span data-ttu-id="349f3-123">Управление пространствами имен в XML-документе</span><span class="sxs-lookup"><span data-stu-id="349f3-123">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
