---
title: "Порядок членов данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 41eb191a08aba0f84a677087a3771b6d8e90efcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="data-member-order"></a><span data-ttu-id="c0616-102">Порядок членов данных</span><span class="sxs-lookup"><span data-stu-id="c0616-102">Data Member Order</span></span>
<span data-ttu-id="c0616-103">В некоторых приложениях полезно знать порядок передачи или предполагаемого приема данных от различных элементов данных (например, порядок, в котором данные появляются в сериализованной форме XML).</span><span class="sxs-lookup"><span data-stu-id="c0616-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="c0616-104">Иногда может потребоваться изменить этот порядок.</span><span class="sxs-lookup"><span data-stu-id="c0616-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="c0616-105">В этом разделе рассматриваются правила упорядочивания.</span><span class="sxs-lookup"><span data-stu-id="c0616-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="c0616-106">Основные правила</span><span class="sxs-lookup"><span data-stu-id="c0616-106">Basic Rules</span></span>  
 <span data-ttu-id="c0616-107">Ниже перечислены основные правила упорядочивания данных.</span><span class="sxs-lookup"><span data-stu-id="c0616-107">The basic rules for data ordering include:</span></span>  
  
-   <span data-ttu-id="c0616-108">Если тип контракта данных является частью иерархии наследования, элементы данных базовых типов всегда идут первыми.</span><span class="sxs-lookup"><span data-stu-id="c0616-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
-   <span data-ttu-id="c0616-109">Затем следуют (в алфавитном порядке) элементы данных текущего типа, для которых не задано свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c0616-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
-   <span data-ttu-id="c0616-110">Затем следуют любые элементы данных, для которых задано свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c0616-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="c0616-111">Они упорядочиваются сначала по значению свойства `Order` и затем по алфавиту, если существует несколько элементов определенного значения `Order`.</span><span class="sxs-lookup"><span data-stu-id="c0616-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="c0616-112">Значения свойства "Order" могут быть пропущены.</span><span class="sxs-lookup"><span data-stu-id="c0616-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="c0616-113">Алфавитный порядок устанавливается посредством вызова метода <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0616-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c0616-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="c0616-114">Examples</span></span>  
 <span data-ttu-id="c0616-115">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="c0616-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="c0616-116">Создаваемый XML-код подобен приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="c0616-116">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>   
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>   
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>   
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0616-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c0616-117">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 [<span data-ttu-id="c0616-118">Эквивалентность контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c0616-118">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="c0616-119">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c0616-119">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
