---
title: Инструмент определения схемы XML и сериализация XML
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: 4c950d84cc95c20c2ae85340a2987ea51bed9570
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979324"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Инструмент определения схемы XML и сериализация XML
Инструмент определения схемы XML ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) устанавливается вместе со средствами .NET Framework в составе пакета средств разработки Windows® (SDK). Этот инструмент служит, главным образом, двум следующим целям.  
  
-   Создание файлов классов C# или Visual Basic, соответствующих определенной схеме языка определения схемы XML (XSD). Инструмент принимает схему XML как аргумент и создает файл с числом классов, которые при сериализации с использованием <xref:System.Xml.Serialization.XmlSerializer> соответствуют схеме. Сведения о том, как использовать средство для создания классов, которые соответствуют определенной схеме, см. в разделе [как: Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
-   Создание документа схемы XML из DLL-файла или EXE-файла. Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML. Сведения о том, как использовать средство для создания документа схемы XML из набора классов см. в разделе [как: Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
 Дополнительные сведения об этом и других средствах см. в разделе [Средства](../../../docs/framework/tools/index.md). Сведения о параметрах этого средства см. в разделе [Инструмент определения схемы XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataSet>
- [Введение в сериализацию XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Инструмент определения схемы XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [Поддержка привязки схемы XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
