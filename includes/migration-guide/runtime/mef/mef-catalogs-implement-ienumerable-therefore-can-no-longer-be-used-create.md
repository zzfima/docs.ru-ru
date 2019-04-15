---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235578"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>). При попытке сериализации каталога MEF происходит вызов исключения.|
|Предложение|Больше не следует использовать MEF для создания сериализатора.|
|Область|Значительно|
|Версия|4.5|
|Тип|Среда выполнения|
