---
title: Удаление узлов из DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: a34b92abc59215c3cb2b94afd88e2e30405b4e9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710314"
---
# <a name="removing-nodes-from-the-dom"></a>Удаление узлов из DOM
Для удаления узла из модели DOM XML-документа используется метод <xref:System.Xml.XmlNode.RemoveChild%2A>, с помощью которого удаляется конкретный узел. При удалении узла метод удаляет поддерево, принадлежащее удаляемому узлу т.е. если это не конечный узел.  
  
 Для удаления нескольких узлов из DOM используется метод <xref:System.Xml.XmlNode.RemoveAll%2A>, удаляющий все дочерние узлы и атрибуты (если применимо) текущего узла.  
  
 При работе с классом <xref:System.Xml.XmlNamedNodeMap> можно удалить узел с помощью метода <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.  
  
 См. дополнительные сведения оь [удалении атрибутов из узла элемента в DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
