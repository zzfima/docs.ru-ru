---
title: Примечания LINQ to XML3
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 5f1940be2fc126ff9e9c7a4cb37e5cc7fc95d3c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "66689940"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="1d5f4-102">Примечания LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1d5f4-102">LINQ to XML Annotations</span></span>

<span data-ttu-id="1d5f4-103">Заметки в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любым XML-компонентом XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="1d5f4-104">Чтобы добавить заметку к компоненту XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, следует вызвать метод <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="1d5f4-105">Заметки получаются по типу.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-105">You retrieve annotations by type.</span></span>

<span data-ttu-id="1d5f4-106">Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="1d5f4-107">Методы</span><span class="sxs-lookup"><span data-stu-id="1d5f4-107">Methods</span></span>

<span data-ttu-id="1d5f4-108">При работе с заметками можно использовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-108">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="1d5f4-109">Метод</span><span class="sxs-lookup"><span data-stu-id="1d5f4-109">Method</span></span>|<span data-ttu-id="1d5f4-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="1d5f4-110">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="1d5f4-111">Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="1d5f4-112">Извлекает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="1d5f4-113">Извлекает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="1d5f4-114">Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="1d5f4-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
