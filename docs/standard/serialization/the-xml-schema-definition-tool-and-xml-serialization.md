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
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Инструмент определения схемы XML и сериализация XML

Инструмент определения XML Schema[(инструмент определения схемы XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)установлен вместе с инструментами&reg; .NET Framework в рамках набора разработки программного обеспечения Windows (SDK). Этот инструмент служит, главным образом, двум следующим целям.  
  
- Создание файлов классов C# или Visual Basic, соответствующих конкретной схеме языка определения схемы XML (XSD). Инструмент принимает схему XML как аргумент и создает файл с числом классов, которые при сериализации с использованием <xref:System.Xml.Serialization.XmlSerializer> соответствуют схеме. Дополнительные сведения об использовании этого средства для создания классов, которые соответствуют определенной схеме, см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
- Создание документа схемы XML из DLL-файла или EXE-файла. Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML. Сведения об использовании этого инструмента для создания документа схемы XML из набора классов см. в разделе [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
Для получения дополнительной информации об использовании инструмента, см [XML Схема Определение инструмент (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataSet>
- [Введение в сериализацию XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [Практическое руководство. Использование инструмента определения схемы XML для создания классов и документов схемы XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [Поддержка привязки схемы XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
