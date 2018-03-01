---
title: "Набор сведений для постсхемной компиляции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 7f1bc7f4-401b-459f-9078-f099cc711fde
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4b59b2b59852190bd19a3c1c9536fadb7b40603e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="post-schema-compilation-infoset"></a><span data-ttu-id="fa0f1-102">Набор сведений для постсхемной компиляции</span><span class="sxs-lookup"><span data-stu-id="fa0f1-102">Post-Schema Compilation Infoset</span></span>
<span data-ttu-id="fa0f1-103">В [документации консорциума W3C по схемам XML](http://go.microsoft.com/fwlink/?linkid=45242) рассматривается информационный набор, который должен предоставляться до и после компиляции схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-103">The [World Wide Web Consortium (W3C) XML Schema Recommendation](http://go.microsoft.com/fwlink/?linkid=45242) discusses the information set (infoset) that must be exposed for pre-schema validation and post-schema compilation.</span></span> <span data-ttu-id="fa0f1-104">Модель XML SOM просматривает информационные наборы до и после вызова метода <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> объекта <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-104">The XML Schema Object Model (SOM) views this exposure before and after the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called.</span></span>  
  
 <span data-ttu-id="fa0f1-105">Информационный набор до проверки по схеме строится во время изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-105">The pre-schema validation infoset is built during the editing of the schema.</span></span> <span data-ttu-id="fa0f1-106">Информационный набор после компиляции схемы формируется после вызова метода <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> объекта <xref:System.Xml.Schema.XmlSchemaSet> во время компиляции схемы и предоставляется в виде свойств.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-106">The post-schema compilation infoset is generated after the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called, during compilation of the schema, and is exposed as properties.</span></span>  
  
 <span data-ttu-id="fa0f1-107">Модель SOM - это модель объектов, представляющая информационные наборы до и после компиляции схемы и состоящая из классов в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-107">The SOM is the object model that represents the pre-schema validation and post-schema compilation infosets; it consists of the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="fa0f1-108">Все свойства чтения и записи классов в пространстве имен <xref:System.Xml.Schema> принадлежат информационному набору до проверки по схеме, а все свойства «только для чтения» классов в пространстве имен <xref:System.Xml.Schema> принадлежат информационному набору после компиляции схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-108">All read and write properties of classes in the <xref:System.Xml.Schema> namespace belong to the pre-schema validation infoset, while all read-only properties of classes in the <xref:System.Xml.Schema> namespace belong to the post-schema compilation infoset.</span></span> <span data-ttu-id="fa0f1-109">Исключением из этого правила являются следующие свойства, которые относятся как к информационному набору до проверки по схеме, так и к информационному набору после компиляции схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-109">The exception to this rule are the following properties, which are both pre-schema validation infoset and post-schema compilation infoset properties.</span></span>  
  
|<span data-ttu-id="fa0f1-110">Класс</span><span class="sxs-lookup"><span data-stu-id="fa0f1-110">Class</span></span>|<span data-ttu-id="fa0f1-111">Свойство.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-111">Property</span></span>|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<span data-ttu-id="fa0f1-112"><xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="fa0f1-112"><xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A></span></span>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<span data-ttu-id="fa0f1-113"><xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A></span><span class="sxs-lookup"><span data-stu-id="fa0f1-113"><xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A></span></span>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 <span data-ttu-id="fa0f1-114">Например, оба класса, <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaComplexType>, имеют свойства `BlockResolved` и `FinalResolved`.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-114">For example, the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaComplexType> classes both have `BlockResolved` and `FinalResolved` properties.</span></span> <span data-ttu-id="fa0f1-115">Эти свойства служат для сохранения значений свойств `Block` и `Final` после компиляции и проверки схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-115">These properties are used to hold the values for the `Block` and `Final` properties after the schema has been compiled and validated.</span></span> <span data-ttu-id="fa0f1-116">Свойства `BlockResolved` и `FinalResolved` доступны только для чтения и являются частью информационного набора после компиляции схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-116">`BlockResolved` and `FinalResolved` are read-only properties that are part of the post-schema compilation infoset.</span></span>  
  
 <span data-ttu-id="fa0f1-117">В следующем примере показано свойство <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> класса <xref:System.Xml.Schema.XmlSchemaElement>, заданное после проверки схемы.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-117">The following example shows the <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> class set after validating the schema.</span></span> <span data-ttu-id="fa0f1-118">До проверки свойство содержит ссылку `null`, и свойству <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> присвоено имя данного типа.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-118">Before validation, the property contains a `null` reference, and the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> is set to the name of the type in question.</span></span> <span data-ttu-id="fa0f1-119">После проверки свойство <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> разрешается в допустимый тип, а объект типа становится доступным через свойство <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa0f1-119">After validation, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> is resolved to a valid type, and the type object is available through the <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> property.</span></span>  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fa0f1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fa0f1-120">See Also</span></span>  
 [<span data-ttu-id="fa0f1-121">Модель объектов схемы XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="fa0f1-121">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
