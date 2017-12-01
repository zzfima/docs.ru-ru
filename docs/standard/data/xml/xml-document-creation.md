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
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a>Создание XML-документа
XML-документ можно создать двумя способами. Один способ — создать **XmlDocument** без параметров. Другим способом является создание **XmlDocument** и его передача классу XmlNameTable в качестве параметра. В следующем примере показано, как создать новый, пустой **XmlDocument** без параметров.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 После создания документа, можно загрузить его с данными из строки, потока, URL-адрес, средства чтения текста, или **XmlReader** производного класса с помощью **загрузить** метод. Имеется также другой метод загрузки, **LoadXML** метод, который считывает XML из строки. Дополнительные сведения о различных **нагрузки** методов, см. [считывание XML-документа в DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Отсутствует класс с именем **XmlNameTable**. Он является таблицей атомарных объектов строки. Эта таблица предоставляет средству синтаксического анализа XML эффективный способ использовать один и тот же строковый объект для всех повторяющихся имен элементов и атрибутов в XML-документе. **XmlNameTable** создается автоматически, когда документ создается, как показано выше, а загружается с именами элементов и атрибутов при загрузке документа. Если уже есть документ с именем таблицы, и эти имена могут быть полезны в другом документе, можно создать новый документ с помощью **нагрузки** метода, принимающего **XmlNameTable** как параметр. При создании документа с помощью этого метода, он использует существующую **XmlNameTable** со всеми атрибутами и элементами, уже загруженными из другого документа. Это можно использовать для эффективного сравнения имен элементов и атрибутов. Дополнительные сведения о **XmlNameTable**, в разделе [сравнение объекта с помощью класса XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Справочную информацию см. в разделе <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
