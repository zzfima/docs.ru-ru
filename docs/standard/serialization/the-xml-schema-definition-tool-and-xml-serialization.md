---
title: Инструмент определения схемы XML и сериализация XML
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: b51b9a0112893d9a7838155f4af051e7079c8cdd
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588392"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="8e3cf-102">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="8e3cf-102">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="8e3cf-103">Инструмент определения XML Schema[(инструмент определения схемы XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)установлен вместе с инструментами&reg; .NET Framework в рамках набора разработки программного обеспечения Windows (SDK).</span><span class="sxs-lookup"><span data-stu-id="8e3cf-103">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="8e3cf-104">Этот инструмент служит, главным образом, двум следующим целям.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-104">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="8e3cf-105">Создание файлов классов C# или Visual Basic, соответствующих конкретной схеме языка определения схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="8e3cf-105">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="8e3cf-106">Инструмент принимает схему XML как аргумент и создает файл с числом классов, которые при сериализации с использованием <xref:System.Xml.Serialization.XmlSerializer> соответствуют схеме.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-106">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="8e3cf-107">Дополнительные сведения об использовании этого средства для создания классов, которые соответствуют определенной схеме, см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="8e3cf-107">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="8e3cf-108">Создание документа схемы XML из DLL-файла или EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-108">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="8e3cf-109">Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML.</span><span class="sxs-lookup"><span data-stu-id="8e3cf-109">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="8e3cf-110">Сведения об использовании этого инструмента для создания документа схемы XML из набора классов см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="8e3cf-110">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="8e3cf-111">Для получения дополнительной информации об использовании инструмента, см [XML Схема Определение инструмент (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8e3cf-111">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3cf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8e3cf-112">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="8e3cf-113">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="8e3cf-113">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="8e3cf-114">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="8e3cf-114">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="8e3cf-115">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="8e3cf-115">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="8e3cf-116">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="8e3cf-116">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="8e3cf-117">Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML</span><span class="sxs-lookup"><span data-stu-id="8e3cf-117">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- <span data-ttu-id="8e3cf-118">[Поддержка привязки схемы XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8e3cf-118">[XML Schema Binding Support](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
