---
title: XDR-проверка с помощью XmlSchemaCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 72bb3c2badef5262907e2e4fa8b461b576e8867d
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934171"
---
# <a name="xdr-validation-with-xmlschemacollection"></a><span data-ttu-id="90dcc-102">XDR-проверка с помощью XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="90dcc-102">XDR Validation with XmlSchemaCollection</span></span>

<span data-ttu-id="90dcc-103">Схема XDR, по которой выполняется проверка, хранится в коллекции **XmlSchemaCollection**. Она связана с URI-кодом пространства имен, который был указан во время добавления схемы в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="90dcc-103">If the XML-Data Reduced (XDR) schema you are validating against is stored in the **XmlSchemaCollection**, it is associated with the namespace URI specified when the schema was added to the collection.</span></span> <span data-ttu-id="90dcc-104">Объект **XmlValidatingReader** сопоставляет URI-код пространства имен в XML-документе со схемой, соответствующей этому URI-коду в коллекции.</span><span class="sxs-lookup"><span data-stu-id="90dcc-104">**XmlValidatingReader** maps the namespace URI in the XML document to the schema that corresponds to that URI in the collection.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90dcc-105">Класс <xref:System.Xml.Schema.XmlSchemaCollection> устарел и заменен классом <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="90dcc-105">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="90dcc-106">Дополнительные сведения о классе <xref:System.Xml.Schema.XmlSchemaSet> см. в руководстве по [использованию XmlSchemaSet для компиляции схемы](xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="90dcc-106">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](xmlschemaset-for-schema-compilation.md).</span></span>

<span data-ttu-id="90dcc-107">Например, если корневым элементом XML-документа является `<bookstore xmlns="urn:newbooks-schema">`, при добавлении схемы в коллекцию **XmlSchemaCollection** она будет ссылаться на то же пространство имен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="90dcc-107">For example, if the root element of the XML document is `<bookstore xmlns="urn:newbooks-schema">`, when the schema is added to the **XmlSchemaCollection** it references the same namespace, as follows:</span></span>

```
xsc.Add("urn:newbooks-schema", "newbooks.xdr")
```

<span data-ttu-id="90dcc-108">В следующем примере кода создается объект **XmlValidatingReader**, который принимает объект **XmlTextReader** и добавляет схему XDR HeadCount.xdr в коллекцию **XmlSchemaCollection**.</span><span class="sxs-lookup"><span data-stu-id="90dcc-108">The following code example creates an **XmlValidatingReader** that takes an **XmlTextReader** and adds an XDR schema, HeadCount.xdr, to the **XmlSchemaCollection**.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Xml
Imports System.Xml.Schema

Namespace ValidationSample

   Class Sample

      Public Shared Sub Main()
         Dim tr As New XmlTextReader("HeadCount.xml")
         Dim vr As New XmlValidatingReader(tr)

         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr")
         vr.ValidationType = ValidationType.XDR
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler

         While vr.Read()
            PrintTypeInfo(vr)
            If vr.NodeType = XmlNodeType.Element Then
               While vr.MoveToNextAttribute()
                  PrintTypeInfo(vr)
               End While
            End If
         End While
         Console.WriteLine("Validation finished")
      End Sub
      ' Main

      Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)
         If Not (vr.SchemaType Is Nothing) Then
            If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then
               Dim value As Object = vr.ReadTypedValue()
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value)
            End If
         End If
      End Sub
      ' PrintTypeInfo

      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)
         Console.WriteLine("***Validation error")
         Console.WriteLine("Severity:{0}", args.Severity)
         Console.WriteLine("Message:{0}", args.Message)
      End Sub
      ' ValidationHandler
   End Class
   ' Sample
End Namespace
' ValidationSample
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Schema;

namespace ValidationSample
{
   class Sample
   {
      public static void Main()
      {
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");
         XmlValidatingReader vr = new XmlValidatingReader(tr);

         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");
         vr.ValidationType = ValidationType.XDR;
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);

         while(vr.Read())
         {
            PrintTypeInfo(vr);
            if(vr.NodeType == XmlNodeType.Element)
            {
               while(vr.MoveToNextAttribute())
                  PrintTypeInfo(vr);
            }
         }
         Console.WriteLine("Validation finished");
      }

      public static void PrintTypeInfo(XmlValidatingReader vr)
      {
         if(vr.SchemaType != null)
         {
            if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)
            {
               object value = vr.ReadTypedValue();
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value);
            }
         }
      }

      public static void ValidationHandler(object sender, ValidationEventArgs args)
      {
         Console.WriteLine("***Validation error");
         Console.WriteLine("\tSeverity:{0}", args.Severity);
         Console.WriteLine("\tMessage:{0}", args.Message);
      }
   }
}
```

<span data-ttu-id="90dcc-109">Ниже описано содержимое проверяемого входного файла *HeadCount.xml*:</span><span class="sxs-lookup"><span data-stu-id="90dcc-109">The following outlines the contents of the input file, *HeadCount.xml*, to be validated:</span></span>

```xml
<!--Load HeadCount.xdr in SchemaCollection for Validation-->
<HeadCount xmlns='xdrHeadCount'>
   <Name>Waldo Pepper</Name>
   <Name>Red Pepper</Name>
</HeadCount>
```

<span data-ttu-id="90dcc-110">Ниже описано содержимое файла XDR-схемы *HeadCount.xdr*, по которому выполняется проверка.</span><span class="sxs-lookup"><span data-stu-id="90dcc-110">The following outlines the contents of the XDR schema file, *HeadCount.xdr*, to be validated against:</span></span>

```xml
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">
   <ElementType name="Name" content="textOnly"/>
   <AttributeType name="Bldg" default="2"/>
   <ElementType name="HeadCount" content="eltOnly">
      <element type="Name"/>
      <attribute type="Bldg"/>
   </ElementType>
</Schema>
```

## <a name="see-also"></a><span data-ttu-id="90dcc-111">См. также</span><span class="sxs-lookup"><span data-stu-id="90dcc-111">See Also</span></span>

<xref:System.Xml.XmlValidatingReader.ValidationType%2A>  
[<span data-ttu-id="90dcc-112">Компиляция схемы XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="90dcc-112">XmlSchemaCollection Schema Compilation</span></span>](xmlschemacollection-schema-compilation.md)  