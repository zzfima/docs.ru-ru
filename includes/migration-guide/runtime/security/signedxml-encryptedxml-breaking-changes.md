---
ms.openlocfilehash: 68da7216890da1819a994161507355a0b5ea1f9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857556"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Критические изменения в SignedXml и EncryptedXml

|   |   |
|---|---|
|Подробнее|Исправления системы безопасности в .NET Framework 4.6.2 для <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> и <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> привели к различиям в поведении во время выполнения. Например:<ul><li>Если документ содержит несколько элементов с одинаковым атрибутом <code>id</code>, один из которых является целевым корнем подписи, такой документ будет считаться недействительным.</li><li>Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XPath в ссылках.</li><li>Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XSLT в ссылках.</li><li>Любая программа, использующая удаленные с внешнего ресурса подписи, не сможет сделать это.</li></ul>|
|Предложение|Разработчикам следует изучить, как используются <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> и производные от <xref:System.Security.Cryptography.Xml.Transform> типы, поскольку получатель документа не всегда сможет обработать его.|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
