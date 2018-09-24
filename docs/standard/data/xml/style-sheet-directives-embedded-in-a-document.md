---
title: Директивы таблицы стилей, встроенные в документ
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65987c5e29d593758b21259d6367202c882df2de
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45742652"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>Директивы таблицы стилей, встроенные в документ

Иногда существующий XML содержит директивы таблицы стилей `<?xml:stylesheet?>`. Обозреватель Microsoft Internet Explorer обрабатывает этот синтаксис как альтернативу `<?xml-stylesheet?>`. Если данные XML содержат директиву `<?xml:stylesheet?>`, как показано в следующем примере, при попытке загрузить эти данные в модель XML DOM будет сформировано исключение.

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

Это происходит потому, что конструкция `<?xml:stylesheet?>` с точки зрения модели DOM представляет собой недопустимую инструкцию **ProcessingInstruction**. Согласно спецификации пространства имен в XML, инструкции **ProcessingInstruction** могут быть только именами, не содержащими двоеточий (NCNames), в противоположность полным именам (QNames).

Согласно разделу 6 спецификации пространств имен в XML наличие методов **Load** и **LoadXml** обеспечивает выполнение в документе следующих условий:

- Все типы элементов и имена атрибутов содержат одно двоеточие или не содержат ни одного.

- Имена сущностей, цели инструкции ProcessingInstruction и имена нотаций не могут содержать двоеточий.

Поскольку конструкция `<?xml:stylesheet?>` содержит двоеточие, это является нарушением второго правила.

Согласно рекомендации консорциума W3C [Связь таблиц стилей с XML-документами версии 1.0](https://www.w3.org/TR/xml-stylesheet/), инструкция по обработке, связывающая таблицу стилей XSLT с XML-документом, выглядит следующим образом: `<?xml-stylesheet?>`, то есть двоеточие заменено на тире.

## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](xml-document-object-model-dom.md)
