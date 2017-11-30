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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a>Создание новых ссылок на сущности
**CreateEntityReference** метод создает новый **XmlEntityReference** узла. Модель DOM определяет, было ли уже декларировано имя сущности, на которую указывает ссылка. При наличии дочерних узлов **XmlEntityReference** узла копируются из узел декларации сущности. Если совпадающая декларация сущности отсутствует, пустой текстовый узел прикрепляется как единственный дочерний узел узла ссылки на сущность. Так как дочерние узлы **XmlEntityReference** узла являются копиями других узлов, эти дочерние узлы доступны только для чтения и не может быть изменено.  
  
 При копировании узлов в области в точке ссылки на сущность может быть пространство имен. Это пространство имен влияет на конфигурацию всех формируемых элементов или узлов атрибутов.  
  
> [!NOTE]
>  Модель DOM добавляет дочерние узлы для **EntityReference** только при вставке **EntityReference** узел в документе. Вновь созданные **EntityReference** узлы не имеют дочерних узлов.  
  
 Несмотря на то что **XmlDataDocument** является производным классом от **XmlDocument**, **XmlDataDocument** не поддерживает создание ссылок на сущности. Это вызвано **EntityReference** дочерние элементы доступны только для чтения. Дочерние элементы **EntityReference** узел может охватывать несколько областей. В этом случае часть строки, связанные с область, которая содержит часть **EntityReference** будут доступны только для чтения.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
