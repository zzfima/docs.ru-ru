---
title: Изменение деклараций пространств имен в XML-документе
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: b8aa670764deb8e77cfb67fd16dbcf8b1cc9b4c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711133"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Изменение деклараций пространств имен в XML-документе
Класс **XmlDocument** представляет декларацию пространств имен и атрибуты **xmlns** как часть модели DOM. Они хранятся в объекте **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов. Изменение этих атрибутов не влияет на свойства **Name**, **NamespaceURI** и **Prefix** других узлов, уже находящихся в дереве. Например, если загрузить следующий документ, то элемент `test` имеет значение **NamespaceURI** `123.`  
  
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
  
 Аналогичным образом, если добавить другой атрибут `xmlns` к элементу `doc`, как показано ниже, элемент `test` все еще имеет `123`**NamespaceURI** .  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Поэтому изменение атрибутов `xmlns` не оказывает никакого влияния, пока объект **XmlDocument** не будет сохранен и перезагружен.  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
