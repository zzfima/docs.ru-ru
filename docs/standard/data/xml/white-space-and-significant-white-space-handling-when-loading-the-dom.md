---
title: "Обработка незначительных и значительных пробелов при загрузке DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Обработка незначительных и значительных пробелов при загрузке DOM
При загрузке документа можно задать параметр, чтобы сохранить пробел и создать **XmlWhitespace** узлов в дереве документа. Чтобы создать узлы пробелов, задайте **PreserveWhitespace** значение true. Если свойство имеет значение **false**, используемого по умолчанию, узлы пробелов не создаются. Узлы значительные пробелы всегда сохраняются, и **XmlSignificantWhitespace** всегда создаются в памяти для представления этих данных, независимо от значения **PreserveWhitespace** флаг.  
  
 Если документ загружается из средства чтения, задав для **PreserveWhitespace** флаг свойство **XmlDocument** класса влияет на создание **XmlWhitespace** узлов только если **WhitespaceHandling** свойство **XmlTextReader** равно **WhitespaceHandling.None**. Это значение **WhitespaceHandling** свойство для чтения, которое имеет приоритет над значением этого флага в **XmlDocument**. Дополнительные сведения о **XmlSignificantWhitespace**, в разделе <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
