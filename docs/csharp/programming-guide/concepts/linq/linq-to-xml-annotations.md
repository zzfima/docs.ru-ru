---
title: Примечания LINQ to XML3
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 5f1940be2fc126ff9e9c7a4cb37e5cc7fc95d3c3
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689940"
---
# <a name="linq-to-xml-annotations"></a>Примечания LINQ to XML

Заметки в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любым XML-компонентом XML-дерева.

Чтобы добавить заметку к компоненту XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, следует вызвать метод <xref:System.Xml.Linq.XObject.AddAnnotation%2A>. Заметки получаются по типу.

Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.

## <a name="methods"></a>Методы

При работе с заметками можно использовать следующие методы.

|Метод|Описание|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Извлекает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Извлекает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.|
