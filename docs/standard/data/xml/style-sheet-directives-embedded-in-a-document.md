---
title: Директивы таблицы стилей, встроенные в документ
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
ms.openlocfilehash: 19e25ab7262bb006144eea71e74bd7454066b3f6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710158"
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

## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](xml-document-object-model-dom.md)
