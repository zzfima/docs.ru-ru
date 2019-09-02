---
title: Ограничения определения
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 4e0f63776162b60c9333ba47be58ea78a9b6805d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204834"
---
# <a name="inference-limitations"></a>Ограничения определения
Процесс вывода схемы <xref:System.Data.DataSet> из XML-кода может приводиться в различных схемах в зависимости от XML-элементов в каждом документе. Например, рассмотрим следующие XML-документы.  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Для "document1" процесс вывода создает **набор данных** с именем "documentElement" и таблицу с именем "Element1", так как "Element1" является повторяющимся элементом.  
  
 **Объекте** DocumentElement  
  
 **Таблица** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Однако для "Document2" процесс вывода создает **набор данных** с именем "невдатасет" и таблицу с именем "documentElement". Element1 выводится в виде столбца, потому что не имеет атрибутов и дочерних элементов.  
  
 **Объекте** невдатасет  
  
 **Таблица** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Эти два XML-документа, возможно, должны были выдавать одну и ту же схему, но процесс вывода дает значительно различающиеся результаты в зависимости от элементов, содержащихся в каждом документе.  
  
 Чтобы избежать расхождений, которые могут возникнуть при формировании схемы из XML-документа, рекомендуется явно указать схему с помощью языка определения схемы XML (XSD) или сокращенных данных XML (XDR) при загрузке **набора данных** из XML. Дополнительные сведения о явном указании схемы **набора данных** с XML-схемой см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>См. также

- [Определение реляционной структуры DataSet из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка DataSet из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме DataSet из XML](loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
