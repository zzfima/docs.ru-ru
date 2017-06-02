---
title: "Директивы таблицы стилей, встроенные в документ | Microsoft Docs"
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
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Директивы таблицы стилей, встроенные в документ
Иногда существующий XML содержит директивы таблицы стилей `<?xml:stylesheet?>`.  Обозреватель Microsoft Internet Explorer воспринимает этот синтаксис как альтернативу `<?xml-stylesheet?>`.  Если данные XML содержат директиву `<?xml:stylesheet?>`, как показано в следующем примере, при попытке загрузить эти данные в модель XML DOM будет сформировано исключение.  
  
```  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Это происходит потому, что конструкция `<?xml:stylesheet?>` с точки зрения модели DOM представляет собой недопустимую инструкцию **ProcessingInstruction**.  Согласно спецификации пространства имен в XML, инструкции **ProcessingInstruction** могут быть только именами, не содержащими двоеточий \(NCNames\), в противоположность полным именам \(QNames\).  
  
 Согласно разделу 6 спецификации «Пространства имен в XML» соответствие методов **Load** и **LoadXml** спецификации заключается в том, что в документе выполняются следующие условия.  
  
-   Все типы элементов и имена атрибутов содержат одно двоеточие или не содержат ни одного.  
  
-   Имена сущностей, цели инструкции ProcessingInstruction и имена нотаций не могут содержать двоеточий.  
  
 Поскольку конструкция `<?xml:stylesheet?>` содержит двоеточие, это является нарушением второго правила.  
  
 Согласно рекомендации W3C «Связь таблиц стилей с XML\-документами» версии 1.0, расположенной по адресу www.w3.org\/TR\/xml\-stylesheet, инструкция по обработке, связывающая таблицу стилей XSLT с XML\-документом, выглядит следующим образом: `<?xml-stylesheet?>`, то есть двоеточие заменено на тире.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)