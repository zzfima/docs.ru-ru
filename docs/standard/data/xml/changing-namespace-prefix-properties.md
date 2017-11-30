---
title: "Изменение свойств префикса пространства имен"
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
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7ce6e4b705188b9c1d0949703991633e3f450689
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-prefix-properties"></a>Изменение свойств префикса пространства имен
**XmlNode** класс позволяет изменять префикс пространства имен, связанный с данным узлом. Изменение префикса элемента показано в следующем фрагменте кода.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Вывод**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 Изменение префикса узла не меняет его пространства имен. Пространство имен можно задавать только при создании узла. При сохранении дерева новые атрибуты пространства имен можно сохранять с учетом присвоенного префикса. Если нельзя создать новое пространство узлов, префикс изменяется, так что узел сохраняет свое локальное имя и пространство имен. В следующем примере показано добавление атрибута в пространство имен.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Вывод**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 При сохранении дерева в строку, в результате вызова **doc. InnerXml**, `xmlns:a='123'` сохранить пространство имен был добавлен атрибут `test` элемента. Он имел значение `'123'` и сохранил `'123'`.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
