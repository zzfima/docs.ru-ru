---
title: Обработка незначительных и значительных пробелов при загрузке DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d9bbb14320b84a6d417c5c28026b169092de219
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266713"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Обработка незначительных и значительных пробелов при загрузке DOM
При загрузке документа можно установить параметр, требующий сохранять пробелы и создавать узлы **XmlWhitespace** в дереве документа. Чтобы создавать узлы пробелов, задайте для свойства **PreserveWhitespace** значение true. Если свойство имеет значение **false**, используемое по умолчанию, то узлы пробелов не создаются. Узлы существенных пробелов сохраняются всегда, и узлы **XmlSignificantWhitespace** всегда создаются в памяти для представления этих данных, независимо от значения флага **PreserveWhitespace**.  
  
 Если документ загружается из средства чтения, то свойства флага **PreserveWhitespace** для класса **XmlDocument** влияют на создание узлов **XmlWhitespace** только в том случае, когда свойство **WhitespaceHandling** для **XmlTextReader** не имеет значения **WhitespaceHandling.None**. Значение свойства **WhitespaceHandling** в средстве чтения имеет приоритет над значением этого флага для **XmlDocument**. Дополнительные сведения о флаге **XmlSignificantWhitespace** см. в статье <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
