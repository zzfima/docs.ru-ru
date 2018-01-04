---
title: "Сериализуемые типы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c8539a-6a79-4413-b294-896f0957b2cd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2bf272e785968f9116cea20ad0c3f40eb786d1f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="serializable-types"></a><span data-ttu-id="ed5fb-102">Сериализуемые типы</span><span class="sxs-lookup"><span data-stu-id="ed5fb-102">Serializable Types</span></span>
<span data-ttu-id="ed5fb-103">По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует все открытые типы.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-103">By default, the <xref:System.Runtime.Serialization.DataContractSerializer> serializes all publicly visible types.</span></span> <span data-ttu-id="ed5fb-104">Все открытые свойства чтения/записи и поля типа сериализуются.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-104">All public read/write properties and fields of the type are serialized.</span></span>  
  
 <span data-ttu-id="ed5fb-105">Изменить предусмотренное по умолчанию поведение можно, применив к типам и членам атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>. Этим удобно пользоваться в ситуациях, когда разработчик не имеет возможности управлять типами и изменять их для добавления атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-105">You can change the default behavior by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the types and members This feature can be useful in situations in which you have types that are not under your control and cannot be modified to add attributes.</span></span> <span data-ttu-id="ed5fb-106"><xref:System.Runtime.Serialization.DataContractSerializer> распознает такие "неотмеченные" типы.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-106">The <xref:System.Runtime.Serialization.DataContractSerializer> recognizes such "unmarked" types.</span></span>  
  
## <a name="serialization-defaults"></a><span data-ttu-id="ed5fb-107">Параметры сериализации по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ed5fb-107">Serialization Defaults</span></span>  
 <span data-ttu-id="ed5fb-108">Для явного управления сериализацией или настройки сериализации типов и членов можно применять атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-108">You can apply the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to explicitly control or customize the serialization of types and members.</span></span> <span data-ttu-id="ed5fb-109">Эти атрибуты также можно применять к закрытым полям.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-109">In addition, you can apply these attributes to private fields.</span></span> <span data-ttu-id="ed5fb-110">В то же время даже типы, не отмеченные этими атрибутами, сериализуются и десериализуются.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-110">However, even types that are not marked with these attributes are serialized and deserialized.</span></span> <span data-ttu-id="ed5fb-111">Действуют следующие правила и исключения.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-111">The following rules and exceptions apply:</span></span>  
  
-   <span data-ttu-id="ed5fb-112"><xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных из типов без атрибутов, используя свойства по умолчанию только что созданных типов.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-112">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract from types without attributes using the default properties of the newly created types.</span></span>  
  
-   <span data-ttu-id="ed5fb-113">Все открытые поля и свойства с открытыми методами `get` и `set` сериализуются, за исключением членов, к которым применен атрибут <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-113">All public fields, and properties with public `get` and `set` methods are serialized, unless you apply the <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> attribute to that member.</span></span>  
  
-   <span data-ttu-id="ed5fb-114">Семантика сериализации аналогична семантике <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-114">The serialization semantics are similar to those of the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
-   <span data-ttu-id="ed5fb-115">В неотмеченных типах сериализуются только открытые типы с не имеющими параметров конструкторами.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-115">In unmarked types, only public types with constructors that do not have parameters are serialized.</span></span> <span data-ttu-id="ed5fb-116">Исключением из этого правила является объект <xref:System.Runtime.Serialization.ExtensionDataObject>, используемый с интерфейсом <xref:System.Runtime.Serialization.IExtensibleDataObject>.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-116">The exception to this rule is <xref:System.Runtime.Serialization.ExtensionDataObject> used with the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span>  
  
-   <span data-ttu-id="ed5fb-117">Доступные только для чтения поля, свойства без метода `get` или `set` и свойства с внутренними или закрытыми методами `set` или `get` не сериализуются.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-117">Read-only fields, properties without a `get` or `set` method, and properties with internal or private `set` or `get` methods are not serialized.</span></span> <span data-ttu-id="ed5fb-118">Такие свойства игнорируются без вызова исключения, кроме случаев с доступными только для возвращения коллекциями.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-118">Such properties are ignored and no exception is thrown, except in the case of get-only collections.</span></span>  
  
-   <span data-ttu-id="ed5fb-119">Атрибуты <xref:System.Xml.Serialization.XmlSerializer> (такие как `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude` и т. д.) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-119"><xref:System.Xml.Serialization.XmlSerializer> attributes (such as `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude`, and so on) are ignored.</span></span>  
  
-   <span data-ttu-id="ed5fb-120">Если не применить к типу атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, все члены в этом типе, к которым применен атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, игнорируются сериализатором.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-120">If you do not apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a given type, the serializer ignores any member in that type to which the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute is applied.</span></span>  
  
-   <span data-ttu-id="ed5fb-121">Свойство <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> поддерживается в типах, не отмеченных атрибутом <xref:System.Runtime.Serialization.DataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-121">The <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> property is supported in types not marked with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute.</span></span> <span data-ttu-id="ed5fb-122">Это подразумевает поддержку атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute> на неотмеченных типах.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-122">This includes support for the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute on unmarked types.</span></span>  
  
-   <span data-ttu-id="ed5fb-123">Чтобы исключить из процесса сериализации открытые члены, свойства или поля, применяйте к таким членам атрибут <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-123">To "opt out" of the serialization process for public members, properties, or fields, apply the <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> attribute to that member.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="ed5fb-124">Наследование</span><span class="sxs-lookup"><span data-stu-id="ed5fb-124">Inheritance</span></span>  
 <span data-ttu-id="ed5fb-125">Неотмеченные типы (типы без атрибута <xref:System.Runtime.Serialization.DataContractAttribute>) могут наследоваться от типов, имеющих этот атрибут. В то же время обратное невозможно: типы с атрибутом от неотмеченных типов наследоваться не могут.</span><span class="sxs-lookup"><span data-stu-id="ed5fb-125">Unmarked types (types without the <xref:System.Runtime.Serialization.DataContractAttribute> attribute) can inherit from types that do have this attribute; however, the reverse is not permitted: types with the attribute cannot inherit from unmarked types.</span></span> <span data-ttu-id="ed5fb-126">Это правило применяется главным образом для обеспечения обратной совместимости с кодом, написанным в более ранних версиях [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed5fb-126">This rule is enforced primarily to ensure backward compatibility with code written in earlier versions of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5fb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ed5fb-127">See Also</span></span>  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="ed5fb-128">Типы, поддерживаемые сериализатором контракта данных</span><span class="sxs-lookup"><span data-stu-id="ed5fb-128">Types Supported by the Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
