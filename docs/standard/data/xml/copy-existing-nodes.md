---
title: Копирование существующих узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: fb9ccd7b16d00355ba87bb32f5447906feeecd94
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711068"
---
# <a name="copy-existing-nodes"></a>Копирование существующих узлов
Модель XML DOM включает множество методов и свойств, которые можно использовать для выбора узла, например **SelectSingleNode**, **ChildNodes[int i]** , **Attributes[int i]** . После выбора узла его можно вставить в дерево с помощью одного из методов вставки, допустимых для данного типа узла. Единственное ограничение при выполнении операции вставки узла в дерево состоит в том, что по ее завершении документ должен оставаться документом правильного формата. При вставке существующего узла в дерево DOM узел удаляется из своей исходной позиции и добавляется в целевую позицию.  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
