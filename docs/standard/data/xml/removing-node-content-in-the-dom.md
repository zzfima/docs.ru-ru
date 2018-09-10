---
title: Удаление содержимого узла в DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 737766586ee920a87c25dd42896bdfb14ae69d98
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44205222"
---
# <a name="removing-node-content-in-the-dom"></a>Удаление содержимого узла в DOM
Для типов узлов, наследующих от <xref:System.Xml.XmlCharacterData>, являющихся типами узлов <xref:System.Xml.XmlComment>,<xref:System.Xml.XmlText>,<xref:System.Xml.XmlCDataSection>,<xref:System.Xml.XmlWhitespace> и <xref:System.Xml.XmlSignificantWhitespace>, можно удалить символы с помощью метода <xref:System.Xml.XmlCharacterData.DeleteData%2A>, который удаляет диапазон символов из узла. Если требуется полностью удалить содержимое, нужно удалить узел, содержащий содержимое. Если требуется сохранить узел, содержимое которого неверно, нужно изменить содержимое. См. дополнительные сведения об [изменении узлов, содержимого и значений в документе XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
