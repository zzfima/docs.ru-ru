---
title: "Считывание объявлений сущностей и ссылок на сущности в DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33b3b0589fb9d3cdf550b8d56d82a2bd999a59f6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="9f964-102">Считывание объявлений сущностей и ссылок на сущности в DOM</span><span class="sxs-lookup"><span data-stu-id="9f964-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="9f964-103">Сущность является декларацией, определяющей имя, которое будет использоваться в XML-документе вместо содержимого или разметки.</span><span class="sxs-lookup"><span data-stu-id="9f964-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="9f964-104">Сущность состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="9f964-104">There are two parts to entities.</span></span> <span data-ttu-id="9f964-105">Во-первых, в декларации сущности необходимо связать имя с заменяющим его содержимым.</span><span class="sxs-lookup"><span data-stu-id="9f964-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="9f964-106">Декларация сущности создается с помощью синтаксиса `<!ENTITY name "value">` определения DTD или схемы XML.</span><span class="sxs-lookup"><span data-stu-id="9f964-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="9f964-107">Во-вторых, определенное в декларации сущности имя впоследствии используется в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="9f964-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="9f964-108">При использовании в XML-документе оно называется ссылкой на сущность.</span><span class="sxs-lookup"><span data-stu-id="9f964-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="9f964-109">Например, следующая декларация сущности определяет сущность с именем `publisher`, связанную с содержимым «Microsoft Press».</span><span class="sxs-lookup"><span data-stu-id="9f964-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="9f964-110">В следующем примере показано использование декларации сущности в XML в качестве ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="9f964-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="9f964-111">Некоторые средства синтаксического анализа автоматически раскрывают сущности при загрузке документа в память.</span><span class="sxs-lookup"><span data-stu-id="9f964-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="9f964-112">Поэтому, когда XML-документ считывается в память, декларации сущностей запоминаются и сохраняются.</span><span class="sxs-lookup"><span data-stu-id="9f964-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="9f964-113">Если средство синтаксического анализа впоследствии встречает символы `&;`, определяющие ссылку на общую сущность, оно ищет это имя в таблице деклараций сущностей.</span><span class="sxs-lookup"><span data-stu-id="9f964-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="9f964-114">Ссылка `&publisher;` заменяется содержимым, которое она представляет.</span><span class="sxs-lookup"><span data-stu-id="9f964-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="9f964-115">Используя следующий XML-код,</span><span class="sxs-lookup"><span data-stu-id="9f964-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="9f964-116">раскрывает ссылку на сущность и заменяет `&publisher;` содержимым Microsoft Press, формируя следующий расширенный XML.</span><span class="sxs-lookup"><span data-stu-id="9f964-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="9f964-117">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="9f964-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="9f964-118">Существует много типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="9f964-118">There are many kinds of entities.</span></span> <span data-ttu-id="9f964-119">На следующей схеме показана классификация типов сущности и терминология.</span><span class="sxs-lookup"><span data-stu-id="9f964-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="9f964-120">![блок-схема иерархии типов сущностей](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="9f964-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="9f964-121">По умолчанию реализация модели DOM на платформе Microsoft .NET Framework сохраняет ссылки на сущности и не развертывает их при загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="9f964-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="9f964-122">Это означает, что при загрузке документа в модель DOM создается узел **XmlEntityReference`&publisher;`, содержащий ссылочную переменную** , с дочерними узлами, представляющими содержимое сущности, объявленной в определении DTD.</span><span class="sxs-lookup"><span data-stu-id="9f964-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="9f964-123">Следующая схема на примере объявления сущности `<!ENTITY publisher "Microsoft Press">` демонстрирует узлы **XmlEntity** и **XmlText**, создаваемые на основе этого объявления.</span><span class="sxs-lookup"><span data-stu-id="9f964-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="9f964-124">![узлы, созданные на основе объявления сущности](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="9f964-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="9f964-125">Будут ли раскрываться ссылки на сущности или нет - зависит от вида узлов, создаваемых в дереве модели DOM в памяти.</span><span class="sxs-lookup"><span data-stu-id="9f964-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="9f964-126">Различия между созданными узлами объясняется в статьях [Сохраняемые ссылки на сущности](../../../../docs/standard/data/xml/entity-references-are-preserved.md) и [Разворачиваемые и не сохраняемые ссылки на сущности](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span><span class="sxs-lookup"><span data-stu-id="9f964-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f964-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9f964-127">See Also</span></span>  
 [<span data-ttu-id="9f964-128">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="9f964-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
