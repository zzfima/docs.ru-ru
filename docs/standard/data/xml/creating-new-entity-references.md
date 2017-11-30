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
# <a name="creating-new-entity-references"></a><span data-ttu-id="e868d-102">Создание новых ссылок на сущности</span><span class="sxs-lookup"><span data-stu-id="e868d-102">Creating New Entity References</span></span>
<span data-ttu-id="e868d-103">**CreateEntityReference** метод создает новый **XmlEntityReference** узла.</span><span class="sxs-lookup"><span data-stu-id="e868d-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="e868d-104">Модель DOM определяет, было ли уже декларировано имя сущности, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e868d-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="e868d-105">При наличии дочерних узлов **XmlEntityReference** узла копируются из узел декларации сущности.</span><span class="sxs-lookup"><span data-stu-id="e868d-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="e868d-106">Если совпадающая декларация сущности отсутствует, пустой текстовый узел прикрепляется как единственный дочерний узел узла ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="e868d-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="e868d-107">Так как дочерние узлы **XmlEntityReference** узла являются копиями других узлов, эти дочерние узлы доступны только для чтения и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="e868d-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="e868d-108">При копировании узлов в области в точке ссылки на сущность может быть пространство имен.</span><span class="sxs-lookup"><span data-stu-id="e868d-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="e868d-109">Это пространство имен влияет на конфигурацию всех формируемых элементов или узлов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e868d-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e868d-110">Модель DOM добавляет дочерние узлы для **EntityReference** только при вставке **EntityReference** узел в документе.</span><span class="sxs-lookup"><span data-stu-id="e868d-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="e868d-111">Вновь созданные **EntityReference** узлы не имеют дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="e868d-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="e868d-112">Несмотря на то что **XmlDataDocument** является производным классом от **XmlDocument**, **XmlDataDocument** не поддерживает создание ссылок на сущности.</span><span class="sxs-lookup"><span data-stu-id="e868d-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="e868d-113">Это вызвано **EntityReference** дочерние элементы доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e868d-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="e868d-114">Дочерние элементы **EntityReference** узел может охватывать несколько областей.</span><span class="sxs-lookup"><span data-stu-id="e868d-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="e868d-115">В этом случае часть строки, связанные с область, которая содержит часть **EntityReference** будут доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e868d-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e868d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e868d-116">See Also</span></span>  
 [<span data-ttu-id="e868d-117">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="e868d-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
