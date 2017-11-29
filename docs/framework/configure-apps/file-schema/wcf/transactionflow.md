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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8c40b3a79567ccc1ca5a83631253d3ff6ead0f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="abd1c-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="abd1c-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="abd1c-103">Задает поддержку потока транзакций для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="abd1c-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="abd1c-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="abd1c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="abd1c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="abd1c-105">\<bindings></span></span>  
<span data-ttu-id="abd1c-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="abd1c-106">\<customBinding></span></span>  
<span data-ttu-id="abd1c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="abd1c-107">\<binding></span></span>  
<span data-ttu-id="abd1c-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="abd1c-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abd1c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abd1c-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abd1c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="abd1c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="abd1c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="abd1c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abd1c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="abd1c-112">Attributes</span></span>  
  
|<span data-ttu-id="abd1c-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="abd1c-113">Attribute</span></span>|<span data-ttu-id="abd1c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="abd1c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abd1c-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="abd1c-115">transactionProtocol</span></span>|<span data-ttu-id="abd1c-116">Задает используемый протокол транзакций.</span><span class="sxs-lookup"><span data-stu-id="abd1c-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="abd1c-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="abd1c-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="abd1c-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="abd1c-118">-   OleTransactions</span></span><br /><span data-ttu-id="abd1c-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="abd1c-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="abd1c-120">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="abd1c-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="abd1c-121">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="abd1c-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abd1c-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="abd1c-122">Child Elements</span></span>  
 <span data-ttu-id="abd1c-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="abd1c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abd1c-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="abd1c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="abd1c-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="abd1c-125">Element</span></span>|<span data-ttu-id="abd1c-126">Описание</span><span class="sxs-lookup"><span data-stu-id="abd1c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abd1c-127">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="abd1c-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="abd1c-128">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="abd1c-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abd1c-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="abd1c-129">Remarks</span></span>  
 <span data-ttu-id="abd1c-130">Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="abd1c-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="abd1c-131">Дополнительные сведения об использовании данного элемента конфигурации в разделе [конфигурация транзакции ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="abd1c-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="abd1c-132">При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="abd1c-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="abd1c-133">Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="abd1c-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd1c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="abd1c-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="abd1c-135">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="abd1c-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="abd1c-136">Включение потока транзакций</span><span class="sxs-lookup"><span data-stu-id="abd1c-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="abd1c-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="abd1c-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="abd1c-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="abd1c-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="abd1c-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="abd1c-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="abd1c-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="abd1c-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
