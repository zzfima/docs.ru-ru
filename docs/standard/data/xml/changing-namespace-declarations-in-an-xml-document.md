---
title: "Изменение деклараций пространств имен в XML-документе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Изменение деклараций пространств имен в XML-документе
**XmlDocument** представляет декларацию пространств имен и **xmlns** атрибутов как часть объектной модели документа. Эти значения хранятся в **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов. Изменение этих атрибутов не оказывает никакого влияния **имя**, **NamespaceURI**, и **префикса** других узлов, уже находящихся в дереве. Например, если загрузить документ а затем `test` элемент имеет **NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 При удалении `xmlns` атрибута следующим образом, то `test` по-прежнему содержит элемент **NamespaceURI** из `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Аналогичным образом Если добавить другой `xmlns` атрибут `doc` элемента, как показано ниже, то `test` по-прежнему содержит элемент **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Поэтому изменение `xmlns` атрибуты не действуют, пока не будет сохранен и перезагружен **XmlDocument** объекта.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
