---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 2d1008a4308c9fda5d2291ce704d1f19205e996a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041253"
---
# <a name="transactionflow"></a><span data-ttu-id="bae5a-101">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="bae5a-101">\<transactionFlow></span></span>
<span data-ttu-id="bae5a-102">Задает поддержку потока транзакций для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="bae5a-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="bae5a-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="bae5a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="bae5a-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="bae5a-104">\<bindings></span></span>  
<span data-ttu-id="bae5a-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bae5a-105">\<customBinding></span></span>  
<span data-ttu-id="bae5a-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="bae5a-106">\<binding></span></span>  
<span data-ttu-id="bae5a-107">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="bae5a-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae5a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bae5a-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bae5a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bae5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bae5a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bae5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bae5a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bae5a-111">Attributes</span></span>  
  
|<span data-ttu-id="bae5a-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bae5a-112">Attribute</span></span>|<span data-ttu-id="bae5a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bae5a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bae5a-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="bae5a-114">transactionProtocol</span></span>|<span data-ttu-id="bae5a-115">Задает используемый протокол транзакций.</span><span class="sxs-lookup"><span data-stu-id="bae5a-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="bae5a-116">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bae5a-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bae5a-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="bae5a-117">-   OleTransactions</span></span><br /><span data-ttu-id="bae5a-118">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="bae5a-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="bae5a-119">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="bae5a-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="bae5a-120">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="bae5a-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bae5a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bae5a-121">Child Elements</span></span>  
 <span data-ttu-id="bae5a-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="bae5a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bae5a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bae5a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bae5a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bae5a-124">Element</span></span>|<span data-ttu-id="bae5a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bae5a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bae5a-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="bae5a-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="bae5a-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="bae5a-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bae5a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="bae5a-128">Remarks</span></span>  
 <span data-ttu-id="bae5a-129">Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="bae5a-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="bae5a-130">Дополнительные сведения об использовании этого элемента конфигурации см. в разделе [Конфигурация транзакций ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="bae5a-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="bae5a-131">При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="bae5a-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="bae5a-132">Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="bae5a-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae5a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="bae5a-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bae5a-134">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bae5a-134">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="bae5a-135">Включение потока транзакций</span><span class="sxs-lookup"><span data-stu-id="bae5a-135">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="bae5a-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="bae5a-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bae5a-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="bae5a-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bae5a-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="bae5a-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bae5a-139">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bae5a-139">\<customBinding></span></span>](custombinding.md)
