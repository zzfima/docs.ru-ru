---
title: "Изменение деклараций пространств имен в XML-документе | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Изменение деклараций пространств имен в XML-документе
Класс **XmlDocument** представляет декларацию пространств имен и атрибуты **xmlns** как часть модели DOM.  Они хранятся в объекте **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов.  Изменение этих атрибутов не влияет на свойства **Name**, **NamespaceURI** и **Prefix** других узлов, уже находящихся в дереве.  Например, при загрузке следующего документа свойство **NamespaceURI** элемента `test` будет иметь значение `123.`  
  
```  
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
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Поэтому изменение атрибутов `xmlns` не оказывает никакого влияния, пока объект **XmlDocument** не будет сохранен и перезагружен.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)