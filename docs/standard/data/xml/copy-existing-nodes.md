---
title: "Копирование существующих узлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c026d9f825375d74d53d5cc46969ff0f713bab1c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="copy-existing-nodes"></a>Копирование существующих узлов
Модель XML DOM включает множество методов и свойств, которые можно использовать для выбора узла, например **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**. После выбора узла его можно вставить в дерево с помощью одного из методов вставки, допустимых для данного типа узла. Единственное ограничение при выполнении операции вставки узла в дерево состоит в том, что по ее завершении документ должен оставаться документом правильного формата. При вставке существующего узла в дерево DOM узел удаляется из своей исходной позиции и добавляется в целевую позицию.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
