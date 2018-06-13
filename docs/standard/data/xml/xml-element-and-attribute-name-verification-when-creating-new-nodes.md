---
title: Проверка имен XML-элементов и атрибутов при создании новых узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de11c190310dec90bd23d044f77d0c38e3a34fcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568853"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Проверка имен XML-элементов и атрибутов при создании новых узлов
Модель XML DOM проверяет допустимость имен при создании новых узлов элементов или узлов атрибутов. Если имена содержат недопустимые символы, возникает исключение. Чтобы гарантировать допустимость и правильную кодировку имен, необходимо использовать класс **XmlConvert** для кодирования и декодирования имен на уровне приложения. Класс **XmlWriter** содержит методы, которые выполняют дополнительную работу, чтобы обеспечить формирование XML-документов правильного формата.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
