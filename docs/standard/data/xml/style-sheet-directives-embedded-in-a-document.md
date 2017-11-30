---
title: "Директивы таблицы стилей, встроенные в документ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>Директивы таблицы стилей, встроенные в документ
Иногда существующий XML содержит директивы таблицы стилей `<?xml:stylesheet?>`. Microsoft Internet Explorer в качестве альтернативы принимает это `<?xml-stylesheet?>` синтаксиса. Если данные XML содержат директиву `<?xml:stylesheet?>`, как показано в следующем примере, при попытке загрузить эти данные в модель XML DOM будет сформировано исключение.  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Это происходит потому, что `<?xml:stylesheet?>` представляет собой недопустимую **ProcessingInstruction** с моделью DOM. Любой **ProcessingInstruction**, согласно спецификации пространства имен в XML, может быть только имена без двоеточий (NCNames), противоположность полным именам (QNames).  
  
 Согласно разделу 6 спецификации пространства имен в XML, эффект отсутствия **нагрузки** и **LoadXml** методы соответствует спецификации, находится в документе:  
  
-   Все типы элементов и имена атрибутов содержат одно двоеточие или не содержат ни одного.  
  
-   Имена сущностей, цели инструкции ProcessingInstruction и имена нотаций не могут содержать двоеточий.  
  
 Поскольку конструкция `<?xml:stylesheet?>` содержит двоеточие, это является нарушением второго правила.  
  
 Согласно рекомендации W3C «Связь таблиц стилей с XML-документами» версии 1.0, расположенной по адресу www.w3.org/TR/xml-stylesheet, инструкция по обработке, связывающая таблицу стилей XSLT с XML-документом, выглядит следующим образом: `<?xml-stylesheet?>`, то есть двоеточие заменено на тире.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
