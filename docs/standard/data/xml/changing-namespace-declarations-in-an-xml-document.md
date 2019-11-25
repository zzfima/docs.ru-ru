---
title: Изменение деклараций пространств имен в XML-документе
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5457eab1f34eb3e7424d508509f5dd6a42ffb51f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976939"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Изменение деклараций пространств имен в XML-документе
Класс **XmlDocument** представляет декларацию пространств имен и атрибуты **xmlns** как часть модели DOM. Они хранятся в объекте **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов. Изменение этих атрибутов не влияет на свойства **Name**, **NamespaceURI** и **Prefix** других узлов, уже находящихся в дереве. Например, при загрузке следующего документа свойство `test`NamespaceURI**элемента** будет иметь значение `123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Если удалить атрибут `xmlns` следующим образом, то элемент `test` все равно будет содержать свойство **NamespaceURI**, которое имеет значение `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Точно так же, если добавить другой атрибут `xmlns` в элемент `doc` следующим образом, элемент `test` все равно будет содержать свойство **NamespaceURI**, которое имеет значение `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Поэтому изменение атрибутов `xmlns` не оказывает никакого влияния, пока объект **XmlDocument** не будет сохранен и перезагружен.  
  
## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
