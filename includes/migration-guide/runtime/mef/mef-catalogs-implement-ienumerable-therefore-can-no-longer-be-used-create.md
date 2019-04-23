---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804968"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>). При попытке сериализации каталога MEF происходит вызов исключения.|
|Предложение|Больше не следует использовать MEF для создания сериализатора.|
|Область|Значительно|
|Версия|4.5|
|Тип|Среда выполнения|
