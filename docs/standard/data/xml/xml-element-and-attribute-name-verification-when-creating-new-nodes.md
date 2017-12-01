---
title: "Проверка имен XML-элементов и атрибутов при создании новых узлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Проверка имен XML-элементов и атрибутов при создании новых узлов
Модель XML DOM проверяет допустимость имен при создании новых узлов элементов или узлов атрибутов. Если имена содержат недопустимые символы, возникает исключение. Чтобы убедиться, что имена являются допустимым и кодированный правильно, необходимо использовать **XmlConvert** класса имя кодирования и декодирования его на уровне приложения. **XmlWriter** содержит методы, которые выполняют дополнительную работу, чтобы убедиться в правильности XML-кода создается.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
