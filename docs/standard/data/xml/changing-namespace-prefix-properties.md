---
title: Изменение свойств префикса пространства имен
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3f41ba7281d67cc2ce848597926f5efebf4d489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568697"
---
# <a name="changing-namespace-prefix-properties"></a>Изменение свойств префикса пространства имен
Класс **XmlNode** позволяет изменять префикс пространства имен, связанный с данным узлом. Изменение префикса элемента показано в следующем фрагменте кода.  
  
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
  
 При сохранении дерева в виде строки с помощью метода **doc.InnerXml** был добавлен атрибут `xmlns:a='123'`, чтобы сохранить пространство имен элемента `test`. Он имел значение `'123'` и сохранил `'123'`.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
