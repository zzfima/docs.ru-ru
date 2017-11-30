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
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6370db06cbe7ff8d46258b0315059f5c37587fea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="aaff3-102">Считывание объявлений сущностей и ссылок на сущности в DOM</span><span class="sxs-lookup"><span data-stu-id="aaff3-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="aaff3-103">Сущность является декларацией, определяющей имя, которое будет использоваться в XML-документе вместо содержимого или разметки.</span><span class="sxs-lookup"><span data-stu-id="aaff3-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="aaff3-104">Сущность состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="aaff3-104">There are two parts to entities.</span></span> <span data-ttu-id="aaff3-105">Во-первых, в декларации сущности необходимо связать имя с заменяющим его содержимым.</span><span class="sxs-lookup"><span data-stu-id="aaff3-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="aaff3-106">Декларация сущности создается с помощью синтаксиса `<!ENTITY name "value">` определения DTD или схемы XML.</span><span class="sxs-lookup"><span data-stu-id="aaff3-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="aaff3-107">Во-вторых, определенное в декларации сущности имя впоследствии используется в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="aaff3-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="aaff3-108">При использовании в XML-документе оно называется ссылкой на сущность.</span><span class="sxs-lookup"><span data-stu-id="aaff3-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="aaff3-109">Например, следующая декларация сущности определяет сущность с именем `publisher`, связанную с содержимым «Microsoft Press».</span><span class="sxs-lookup"><span data-stu-id="aaff3-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="aaff3-110">В следующем примере показано использование декларации сущности в XML в качестве ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="aaff3-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="aaff3-111">Некоторые средства синтаксического анализа автоматически раскрывают сущности при загрузке документа в память.</span><span class="sxs-lookup"><span data-stu-id="aaff3-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="aaff3-112">Поэтому, когда XML-документ считывается в память, декларации сущностей запоминаются и сохраняются.</span><span class="sxs-lookup"><span data-stu-id="aaff3-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="aaff3-113">Если средство синтаксического анализа впоследствии встречает символы `&;`, определяющие ссылку на общую сущность, оно ищет это имя в таблице деклараций сущностей.</span><span class="sxs-lookup"><span data-stu-id="aaff3-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="aaff3-114">Ссылка `&publisher;` заменяется содержимым, которое она представляет.</span><span class="sxs-lookup"><span data-stu-id="aaff3-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="aaff3-115">Используя следующий XML-код,</span><span class="sxs-lookup"><span data-stu-id="aaff3-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="aaff3-116">раскрывает ссылку на сущность и заменяет `&publisher;` содержимым Microsoft Press, формируя следующий расширенный XML.</span><span class="sxs-lookup"><span data-stu-id="aaff3-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="aaff3-117">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="aaff3-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="aaff3-118">Существует много типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="aaff3-118">There are many kinds of entities.</span></span> <span data-ttu-id="aaff3-119">На следующей схеме показана классификация типов сущности и терминология.</span><span class="sxs-lookup"><span data-stu-id="aaff3-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="aaff3-120">![Блок-схема иерархии типов сущностей](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="aaff3-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="aaff3-121">По умолчанию реализация платформы Microsoft .NET Framework модель объектов XML документа (DOM) является сохранение ссылки на сущности и не раскрывает их при загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="aaff3-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="aaff3-122">Это означает, как при загрузке документа в DOM **XmlEntityReference** узел, содержащий ссылочную переменную `&publisher;` будет создана, с дочерними узлами, представляющими содержимое сущности, объявленной в DTD.</span><span class="sxs-lookup"><span data-stu-id="aaff3-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="aaff3-123">С помощью `<!ENTITY publisher "Microsoft Press">` на следующей схеме показана декларация сущности **XmlEntity** и **XmlText** узлы, созданные на основе этой декларации.</span><span class="sxs-lookup"><span data-stu-id="aaff3-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="aaff3-124">![узлы, созданные на основе объявления сущностей](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="aaff3-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="aaff3-125">Будут ли раскрываться ссылки на сущности или нет - зависит от вида узлов, создаваемых в дереве модели DOM в памяти.</span><span class="sxs-lookup"><span data-stu-id="aaff3-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="aaff3-126">Различие в формируемых узлов объясняется в разделах [ссылки на сущности сохраняются](../../../../docs/standard/data/xml/entity-references-are-preserved.md) и [, ссылки на сущности раскрываются и не сохраняются](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span><span class="sxs-lookup"><span data-stu-id="aaff3-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaff3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="aaff3-127">See Also</span></span>  
 [<span data-ttu-id="aaff3-128">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="aaff3-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
