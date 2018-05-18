---
title: Копирование существующих узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e7f5638d0d1f7bf450be526d7c295d4bb6a79eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="copy-existing-nodes"></a>Копирование существующих узлов
Модель XML DOM включает множество методов и свойств, которые можно использовать для выбора узла, например **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**. После выбора узла его можно вставить в дерево с помощью одного из методов вставки, допустимых для данного типа узла. Единственное ограничение при выполнении операции вставки узла в дерево состоит в том, что по ее завершении документ должен оставаться документом правильного формата. При вставке существующего узла в дерево DOM узел удаляется из своей исходной позиции и добавляется в целевую позицию.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
