---
title: Считывание объявлений сущностей и ссылок на сущности в DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 986f0f1d6ce20722b85ac0cfa9e3fe3fa351b75e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569659"
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="fbf98-102">Считывание объявлений сущностей и ссылок на сущности в DOM</span><span class="sxs-lookup"><span data-stu-id="fbf98-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="fbf98-103">Сущность является декларацией, определяющей имя, которое будет использоваться в XML-документе вместо содержимого или разметки.</span><span class="sxs-lookup"><span data-stu-id="fbf98-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="fbf98-104">Сущность состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="fbf98-104">There are two parts to entities.</span></span> <span data-ttu-id="fbf98-105">Во-первых, в декларации сущности необходимо связать имя с заменяющим его содержимым.</span><span class="sxs-lookup"><span data-stu-id="fbf98-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="fbf98-106">Декларация сущности создается с помощью синтаксиса `<!ENTITY name "value">` определения DTD или схемы XML.</span><span class="sxs-lookup"><span data-stu-id="fbf98-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="fbf98-107">Во-вторых, определенное в декларации сущности имя впоследствии используется в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="fbf98-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="fbf98-108">При использовании в XML-документе оно называется ссылкой на сущность.</span><span class="sxs-lookup"><span data-stu-id="fbf98-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="fbf98-109">Например, следующая декларация сущности определяет сущность с именем `publisher`, связанную с содержимым «Microsoft Press».</span><span class="sxs-lookup"><span data-stu-id="fbf98-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="fbf98-110">В следующем примере показано использование декларации сущности в XML в качестве ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="fbf98-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="fbf98-111">Некоторые средства синтаксического анализа автоматически раскрывают сущности при загрузке документа в память.</span><span class="sxs-lookup"><span data-stu-id="fbf98-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="fbf98-112">Поэтому, когда XML-документ считывается в память, декларации сущностей запоминаются и сохраняются.</span><span class="sxs-lookup"><span data-stu-id="fbf98-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="fbf98-113">Если средство синтаксического анализа впоследствии встречает символы `&;`, определяющие ссылку на общую сущность, оно ищет это имя в таблице деклараций сущностей.</span><span class="sxs-lookup"><span data-stu-id="fbf98-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="fbf98-114">Ссылка `&publisher;` заменяется содержимым, которое она представляет.</span><span class="sxs-lookup"><span data-stu-id="fbf98-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="fbf98-115">Используя следующий XML-код,</span><span class="sxs-lookup"><span data-stu-id="fbf98-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="fbf98-116">раскрывает ссылку на сущность и заменяет `&publisher;` содержимым Microsoft Press, формируя следующий расширенный XML.</span><span class="sxs-lookup"><span data-stu-id="fbf98-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="fbf98-117">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="fbf98-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="fbf98-118">Существует много типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="fbf98-118">There are many kinds of entities.</span></span> <span data-ttu-id="fbf98-119">На следующей схеме показана классификация типов сущности и терминология.</span><span class="sxs-lookup"><span data-stu-id="fbf98-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="fbf98-120">![блок-схема иерархии типов сущностей](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="fbf98-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="fbf98-121">По умолчанию реализация модели DOM на платформе Microsoft .NET Framework сохраняет ссылки на сущности и не развертывает их при загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="fbf98-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="fbf98-122">Это означает, что при загрузке документа в модель DOM создается узел **XmlEntityReference`&publisher;`, содержащий ссылочную переменную** , с дочерними узлами, представляющими содержимое сущности, объявленной в определении DTD.</span><span class="sxs-lookup"><span data-stu-id="fbf98-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="fbf98-123">Следующая схема на примере объявления сущности `<!ENTITY publisher "Microsoft Press">` демонстрирует узлы **XmlEntity** и **XmlText**, создаваемые на основе этого объявления.</span><span class="sxs-lookup"><span data-stu-id="fbf98-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="fbf98-124">![узлы, созданные на основе объявления сущности](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="fbf98-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="fbf98-125">Будут ли раскрываться ссылки на сущности или нет - зависит от вида узлов, создаваемых в дереве модели DOM в памяти.</span><span class="sxs-lookup"><span data-stu-id="fbf98-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="fbf98-126">Различия между созданными узлами объясняется в статьях [Сохраняемые ссылки на сущности](../../../../docs/standard/data/xml/entity-references-are-preserved.md) и [Разворачиваемые и не сохраняемые ссылки на сущности](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span><span class="sxs-lookup"><span data-stu-id="fbf98-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf98-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fbf98-127">See Also</span></span>  
 [<span data-ttu-id="fbf98-128">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="fbf98-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
