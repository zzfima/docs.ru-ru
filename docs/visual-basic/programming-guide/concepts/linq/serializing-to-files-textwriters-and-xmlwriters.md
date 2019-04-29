---
title: Сериализация в файлы, и объекты textwriters и XmlWriters3
ms.date: 07/20/2015
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
ms.openlocfilehash: 63577d955da89fde0a2320b4cf84414ccbb69c84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786793"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Сериализация в файлы и объекты TextWriters и XmlWriters

XML-деревья можно сериализовать для <xref:System.IO.File>, <xref:System.IO.TextWriter> или для <xref:System.Xml.XmlWriter>.

Любой компонент XML, включая <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement>, можно сериализовать для строки с помощью метода `ToString`.

Если в процессе сериализации в строку необходимо подавить форматирование, эту задачу можно решить с помощью метода <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.

При выполнении сериализации для файла поведение по умолчанию заключается в форматировании (посредством создания отступов) результирующего XML-документа. При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются. Для выполнения сериализации с форматированием нужно использовать одну из перегрузок следующих методов, не принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Если необходимо воздержаться от создания отступов и сохранить не имеющие значения пробелы в XML-дереве, нужно использовать одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Примеры см. в следующем разделе справки.

## <a name="see-also"></a>См. также

- [Сериализация деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
