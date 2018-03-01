---
title: "Создание XML-документа"
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
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea67841e44d8d88d2effec92eb1668142c1510f2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="xml-document-creation"></a>Создание XML-документа
XML-документ можно создать двумя способами. Один из них заключается в создании объекта **XmlDocument** без параметров. Второй включает создание объекта **XmlDocument**, которому нужно в качестве параметра передать XmlNameTable. В следующем примере показано создание пустого объекта **XmlDocument** без параметров.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 После создания документа в него можно с помощью метода **Load** загрузить данные из строки, потока, URL-адреса, текстового модуля чтения или класса, производного от **XmlReader**. Есть еще один метод загрузки: **LoadXML**, который считывает XML из строки. Дополнительные сведения о различных методах **Load** см. в статье [Считывание XML-документа в DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Существует класс с именем **XmlNameTable**. Он является таблицей атомарных объектов строки. Эта таблица предоставляет средству синтаксического анализа XML эффективный способ использовать один и тот же строковый объект для всех повторяющихся имен элементов и атрибутов в XML-документе. Класс **XmlNameTable** автоматически создается при создании документа, как показано выше, и заполняется именами элементов и атрибутов при загрузке этого документа. Если у вас уже есть документ с таблицей имен и эти имена можно применить в другом документе, создайте новый документ с помощью метода **Load**, передав ему в качестве параметра таблицу **XmlNameTable**. Когда документ создается с помощью этого метода, он использует существующую таблицу **XmlNameTable** со всеми атрибутами и элементами, ранее загруженными в нее из другого документа. Это можно использовать для эффективного сравнения имен элементов и атрибутов. Дополнительные сведения о классе **XmlNameTable** см. в таблице [Сравнение объектов с помощью XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Справочную информацию см. в статье <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
