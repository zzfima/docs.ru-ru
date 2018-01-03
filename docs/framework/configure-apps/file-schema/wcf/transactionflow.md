---
title: '&lt;transactionFlow&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3720294ac937c6aa7ce99ab687efa76b2e860abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="74a61-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="74a61-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="74a61-103">Задает поддержку потока транзакций для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="74a61-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="74a61-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="74a61-104">\<system.serviceModel></span></span>  
<span data-ttu-id="74a61-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="74a61-105">\<bindings></span></span>  
<span data-ttu-id="74a61-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="74a61-106">\<customBinding></span></span>  
<span data-ttu-id="74a61-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="74a61-107">\<binding></span></span>  
<span data-ttu-id="74a61-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="74a61-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a61-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74a61-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74a61-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74a61-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74a61-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="74a61-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74a61-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74a61-112">Attributes</span></span>  
  
|<span data-ttu-id="74a61-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="74a61-113">Attribute</span></span>|<span data-ttu-id="74a61-114">Описание</span><span class="sxs-lookup"><span data-stu-id="74a61-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74a61-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="74a61-115">transactionProtocol</span></span>|<span data-ttu-id="74a61-116">Задает используемый протокол транзакций.</span><span class="sxs-lookup"><span data-stu-id="74a61-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="74a61-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="74a61-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="74a61-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="74a61-118">-   OleTransactions</span></span><br /><span data-ttu-id="74a61-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="74a61-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="74a61-120">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="74a61-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="74a61-121">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="74a61-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74a61-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74a61-122">Child Elements</span></span>  
 <span data-ttu-id="74a61-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="74a61-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74a61-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74a61-124">Parent Elements</span></span>  
  
|<span data-ttu-id="74a61-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="74a61-125">Element</span></span>|<span data-ttu-id="74a61-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="74a61-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74a61-127">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="74a61-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="74a61-128">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="74a61-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74a61-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="74a61-129">Remarks</span></span>  
 <span data-ttu-id="74a61-130">Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="74a61-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="74a61-131">Дополнительные сведения об использовании данного элемента конфигурации в разделе [конфигурация транзакции ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="74a61-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="74a61-132">При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="74a61-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="74a61-133">Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="74a61-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a61-134">См. также</span><span class="sxs-lookup"><span data-stu-id="74a61-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="74a61-135">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="74a61-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="74a61-136">Включение потока транзакций</span><span class="sxs-lookup"><span data-stu-id="74a61-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="74a61-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="74a61-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="74a61-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="74a61-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="74a61-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="74a61-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="74a61-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="74a61-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
