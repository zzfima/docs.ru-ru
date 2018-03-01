---
title: "Создание новых ссылок на сущности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76093fbe7095c2aae7caa69147f6181c292ca734
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="creating-new-entity-references"></a>Создание новых ссылок на сущности
Метод **CreateEntityReference** создает новый узел **XmlEntityReference**. Модель DOM определяет, было ли уже декларировано имя сущности, на которую указывает ссылка. Если было, то дочерние узлы узла **XmlEntityReference** копируются из узла декларации сущности. Если совпадающая декларация сущности отсутствует, пустой текстовый узел прикрепляется как единственный дочерний узел узла ссылки на сущность. Так как дочерние узлы узла **XmlEntityReference** являются копиями других узлов, они доступны только для чтения и не могут быть изменены.  
  
 При копировании узлов в области в точке ссылки на сущность может быть пространство имен. Это пространство имен влияет на конфигурацию всех формируемых элементов или узлов атрибутов.  
  
> [!NOTE]
>  Модель DOM добавляет дочерние узлы к узлу **EntityReference** только при вставке в документ узла **EntityReference**. Вновь созданные узлы **EntityReference** не имеют дочерних узлов.  
  
 Хотя класс **XmlDataDocument** является производным от класса **XmlDocument**, класс **XmlDataDocument** не поддерживает создание ссылок на сущности. Это связано с тем, что дочерние узлы **EntityReference** доступны только для чтения. Дочерние узлы узла **EntityReference** могут принадлежать к нескольким областям. В этом случае часть строки, связанная с областью, которая содержит часть узла **EntityReference**, будет доступна только для чтения.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
