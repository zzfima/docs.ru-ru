---
title: Эквивалентность контрактов данных
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], equivalence
ms.assetid: f06f3c7e-c235-4ec1-b200-68142edf1ed1
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aebd21186f7d038dfa5d7c3c65f833d41f4a1f71
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="data-contract-equivalence"></a><span data-ttu-id="44cfd-102">Эквивалентность контрактов данных</span><span class="sxs-lookup"><span data-stu-id="44cfd-102">Data Contract Equivalence</span></span>
<span data-ttu-id="44cfd-103">Чтобы клиент мог успешно отправлять данные определенного типа службе или чтобы служба могла успешно отправлять данные клиенту, отправляемый тип не обязательно должен существовать на принимающей стороне.</span><span class="sxs-lookup"><span data-stu-id="44cfd-103">For a client to successfully send data of a certain type to a service, or a service to successfully send data to a client, the sent type does not necessarily have to exist on the receiving end.</span></span> <span data-ttu-id="44cfd-104">Единственное требование заключается в эквивалентности контрактов данных обоих типов.</span><span class="sxs-lookup"><span data-stu-id="44cfd-104">The only requirement is that the data contracts of both types be equivalent.</span></span> <span data-ttu-id="44cfd-105">(В некоторых случаях строгой эквивалентности не является обязательным, как описано в [управление версиями контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md).)</span><span class="sxs-lookup"><span data-stu-id="44cfd-105">(Sometimes, strict equivalence is not required, as discussed in [Data Contract Versioning](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md).)</span></span>  
  
 <span data-ttu-id="44cfd-106">Чтобы контракты данных были эквивалентны, они должны иметь одинаковые пространство имен и имя.</span><span class="sxs-lookup"><span data-stu-id="44cfd-106">For data contracts to be equivalent, they must have the same namespace and name.</span></span> <span data-ttu-id="44cfd-107">Кроме того, каждый член данных на одной стороне должен иметь эквивалентный член данных на другой стороне.</span><span class="sxs-lookup"><span data-stu-id="44cfd-107">Additionally, each data member on one side must have an equivalent data member on the other side.</span></span>  
  
 <span data-ttu-id="44cfd-108">Чтобы члены данных были эквивалентны, они должны иметь одинаковое имя.</span><span class="sxs-lookup"><span data-stu-id="44cfd-108">For data members to be equivalent, they must have the same name.</span></span> <span data-ttu-id="44cfd-109">Кроме того, они должны представлять один и тот же тип данных, т. е. их контракты данных должны быть эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="44cfd-109">Additionally, they must represent the same type of data; that is, their data contracts must be equivalent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44cfd-110">Обратите внимание, что в именах контрактов данных и пространствах имен, равно как и в именах членов данных, учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="44cfd-110">Note that data contract names and namespaces, as well as data member names, are case-sensitive.</span></span>  
  
 <span data-ttu-id="44cfd-111">Дополнительные сведения о имена контрактов данных и пространства имен, а также имена членов данных см. в разделе [имена контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-names.md).</span><span class="sxs-lookup"><span data-stu-id="44cfd-111">For more information about data contract names and namespaces, as well as data member names, see [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md).</span></span>  
  
 <span data-ttu-id="44cfd-112">Если два типа существуют на одной и той же стороне (отправителя или получателя) и их контракты данных не эквивалентны (например, имеют разные члены данных), не следует давать им одно и то же имя и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="44cfd-112">If two types exist on the same side (sender or receiver) and their data contracts are not equivalent (for example, they have different data members), you should not give them the same name and namespace.</span></span> <span data-ttu-id="44cfd-113">Это может привести к возникновению исключений.</span><span class="sxs-lookup"><span data-stu-id="44cfd-113">Doing so may cause exceptions to be thrown.</span></span>  
  
 <span data-ttu-id="44cfd-114">Контракты данных для следующих типов эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="44cfd-114">The data contracts for the following types are equivalent:</span></span>  
  
 [!code-csharp[C_DataContractNames#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#5)]
 [!code-vb[C_DataContractNames#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#5)]  
  
## <a name="data-member-order-and-data-contract-equivalence"></a><span data-ttu-id="44cfd-115">Эквивалентность порядка членов данных и контрактов данных</span><span class="sxs-lookup"><span data-stu-id="44cfd-115">Data Member Order and Data Contract equivalence</span></span>  
 <span data-ttu-id="44cfd-116">Использование свойства <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> класса <xref:System.Runtime.Serialization.DataMemberAttribute> может повлиять на эквивалентность контрактов данных.</span><span class="sxs-lookup"><span data-stu-id="44cfd-116">Using the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> class may affect data contract equivalence.</span></span> <span data-ttu-id="44cfd-117">Чтобы контракты данных были эквивалентны, члены данных в них должны следовать в одинаковом порядке.</span><span class="sxs-lookup"><span data-stu-id="44cfd-117">The data contracts must have members that appear in the same order to be equivalent.</span></span> <span data-ttu-id="44cfd-118">По умолчанию они следуют в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="44cfd-118">The default order is alphabetical.</span></span> <span data-ttu-id="44cfd-119">Дополнительные сведения см. в разделе [порядок членов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="44cfd-119">For more information, see [Data Member Order](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span></span>  
  
 <span data-ttu-id="44cfd-120">Например, следующий код представляет собой эквивалентные контракты данных.</span><span class="sxs-lookup"><span data-stu-id="44cfd-120">For example, the following code results in equivalent data contracts.</span></span>  
  
 [!code-csharp[C_DataContractNames#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#6)]
 [!code-vb[C_DataContractNames#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#6)]  
  
 <span data-ttu-id="44cfd-121">В то же время следующие примеры не являются эквивалентными контрактами данных.</span><span class="sxs-lookup"><span data-stu-id="44cfd-121">However, the following does not result in an equivalent data contract.</span></span>  
  
 [!code-csharp[C_DataContractNames#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#7)]
 [!code-vb[C_DataContractNames#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#7)]  
  
## <a name="inheritance-interfaces-and-data-contract-equivalence"></a><span data-ttu-id="44cfd-122">Наследование, интерфейсы и эквивалентность контрактов данных</span><span class="sxs-lookup"><span data-stu-id="44cfd-122">Inheritance, Interfaces, and Data Contract Equivalence</span></span>  
 <span data-ttu-id="44cfd-123">При определении эквивалентности контракт данных, наследующий от других контрактов данных, рассматривается так, как будто это просто контракт данных, включающий все члены данных из базового типа.</span><span class="sxs-lookup"><span data-stu-id="44cfd-123">When determining equivalence, a data contract that inherits from another data contract is treated as if it is just one data contract that includes all of the data members from the base type.</span></span> <span data-ttu-id="44cfd-124">Следует помнить, что порядок членов данных должен совпадать, и что члены базового типа должны идти перед членами производного типа.</span><span class="sxs-lookup"><span data-stu-id="44cfd-124">Keep in mind that the order of the data members must match and that base type members precede derived type members in the order.</span></span> <span data-ttu-id="44cfd-125">Кроме того, если, как в следующем примере кода, два члена данных имеют одно и то же значение порядка, эти члены данных располагаются в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="44cfd-125">Furthermore, if, as in the following code example, two data members have the same order value, the ordering for those data members is alphabetical.</span></span> <span data-ttu-id="44cfd-126">Дополнительные сведения см. в разделе [порядок членов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="44cfd-126">For more information, see [Data Member Order](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span></span>  
  
 <span data-ttu-id="44cfd-127">В следующем примере контракт данных для типа `Employee` эквивалентен контракту данных для типа `Worker`.</span><span class="sxs-lookup"><span data-stu-id="44cfd-127">In the following example, the data contract for type `Employee` is equivalent to the data contract for the type `Worker`.</span></span>  
  
 [!code-csharp[C_DataContractNames#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#8)]
 [!code-vb[C_DataContractNames#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#8)]  
  
 <span data-ttu-id="44cfd-128">При передаче параметров и возвращаемых значений между клиентом и службой нельзя отправить контракт данных от базового класса, когда принимающая конечная точка ожидает контракт данных от производного класса.</span><span class="sxs-lookup"><span data-stu-id="44cfd-128">When passing parameters and return values between a client and a service, a data contract from a base class cannot be sent when the receiving endpoint expects a data contract from a derived class.</span></span> <span data-ttu-id="44cfd-129">Это соответствует принципам объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="44cfd-129">This is in accordance with object-oriented programming tenets.</span></span> <span data-ttu-id="44cfd-130">В предыдущем примере объект типа `Person` не может быть отправлено при `Employee` ожидается.</span><span class="sxs-lookup"><span data-stu-id="44cfd-130">In the previous example, an object of type `Person` cannot be sent when an `Employee` is expected.</span></span>  
  
 <span data-ttu-id="44cfd-131">Можно отправить контракт данных от производного класса, когда ожидается контракт данных от базового класса, однако только при условии, что принимающая конечная точка "знает" производный тип путем использования атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="44cfd-131">A data contract from a derived class can be sent when a data contract from a base class is expected, but only if the receiving endpoint "knows" of the derived type using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="44cfd-132">Дополнительные сведения см. в разделе [известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="44cfd-132">For more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="44cfd-133">В предыдущем примере можно отправить объект типа `Employee`, если ожидается объект типа `Person`, однако только если в принимающем коде присутствует атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute> для включения этого типа в список известных типов.</span><span class="sxs-lookup"><span data-stu-id="44cfd-133">In the previous example, an object of type `Employee` can be sent when a `Person` is expected, but only if the receiver code employs the <xref:System.Runtime.Serialization.KnownTypeAttribute> to include it in the list of known types.</span></span>  
  
 <span data-ttu-id="44cfd-134">Если при передаче параметров и возвращаемых значений между приложениями ожидаемый тип представляет собой интерфейс, это эквивалентно тому, что ожидаемый тип принадлежит к типу <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="44cfd-134">When passing parameters and return values between applications, if the expected type is an interface, it is equivalent to the expected type being of type <xref:System.Object>.</span></span> <span data-ttu-id="44cfd-135">Поскольку все типы в конечном итоге наследуются от <xref:System.Object>, все контракты данных в конечном итоге наследуются от контракта данных для <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="44cfd-135">Because every type ultimately derives from <xref:System.Object>, every data contract ultimately derives from the data contract for <xref:System.Object>.</span></span> <span data-ttu-id="44cfd-136">Таким образом, когда ожидается интерфейс, передать можно любой контракт данных.</span><span class="sxs-lookup"><span data-stu-id="44cfd-136">Thus, any data contract type can be passed when an interface is expected.</span></span> <span data-ttu-id="44cfd-137">Необходимы дополнительные действия для успешной работы с интерфейсов. Дополнительные сведения см. в разделе [известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="44cfd-137">Additional steps are required to successfully work with interfaces; for more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44cfd-138">См. также</span><span class="sxs-lookup"><span data-stu-id="44cfd-138">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="44cfd-139">Порядок членов данных</span><span class="sxs-lookup"><span data-stu-id="44cfd-139">Data Member Order</span></span>](../../../../docs/framework/wcf/feature-details/data-member-order.md)  
 [<span data-ttu-id="44cfd-140">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="44cfd-140">Data Contract Known Types</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="44cfd-141">Имена контрактов данных</span><span class="sxs-lookup"><span data-stu-id="44cfd-141">Data Contract Names</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-names.md)
