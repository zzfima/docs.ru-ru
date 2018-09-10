---
title: Проверка имен XML-элементов и атрибутов при создании новых узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 008cf14e63b8458feebf26eaf27be516bb79f933
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216045"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Проверка имен XML-элементов и атрибутов при создании новых узлов
Модель XML DOM проверяет допустимость имен при создании новых узлов элементов или узлов атрибутов. Если имена содержат недопустимые символы, возникает исключение. Чтобы гарантировать допустимость и правильную кодировку имен, необходимо использовать класс **XmlConvert** для кодирования и декодирования имен на уровне приложения. Класс **XmlWriter** содержит методы, которые выполняют дополнительную работу, чтобы обеспечить формирование XML-документов правильного формата.  
  
## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
