---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 626ae03d622221ab3e956bd03898b6cc30482c98
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179157"
---
# <a name="transactionflow"></a><span data-ttu-id="a3697-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="a3697-101">\<transactionFlow></span></span>
<span data-ttu-id="a3697-102">Задает поддержку потока транзакций для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="a3697-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="a3697-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3697-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a3697-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a3697-104">\<bindings></span></span>  
<span data-ttu-id="a3697-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a3697-105">\<customBinding></span></span>  
<span data-ttu-id="a3697-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a3697-106">\<binding></span></span>  
<span data-ttu-id="a3697-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="a3697-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3697-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3697-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3697-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a3697-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a3697-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a3697-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3697-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a3697-111">Attributes</span></span>  
  
|<span data-ttu-id="a3697-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a3697-112">Attribute</span></span>|<span data-ttu-id="a3697-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a3697-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3697-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="a3697-114">transactionProtocol</span></span>|<span data-ttu-id="a3697-115">Задает используемый протокол транзакций.</span><span class="sxs-lookup"><span data-stu-id="a3697-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="a3697-116">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a3697-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3697-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="a3697-117">-   OleTransactions</span></span><br /><span data-ttu-id="a3697-118">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="a3697-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="a3697-119">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="a3697-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="a3697-120">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="a3697-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3697-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a3697-121">Child Elements</span></span>  
 <span data-ttu-id="a3697-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a3697-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3697-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a3697-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a3697-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a3697-124">Element</span></span>|<span data-ttu-id="a3697-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a3697-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3697-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a3697-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a3697-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="a3697-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3697-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="a3697-128">Remarks</span></span>  
 <span data-ttu-id="a3697-129">Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="a3697-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="a3697-130">Дополнительные сведения об использовании данного элемента конфигурации см. в разделе [конфигурация транзакции ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a3697-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a3697-131">При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="a3697-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="a3697-132">Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="a3697-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3697-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a3697-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a3697-134">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a3697-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="a3697-135">Включение потока транзакций</span><span class="sxs-lookup"><span data-stu-id="a3697-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="a3697-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="a3697-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a3697-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="a3697-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a3697-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="a3697-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a3697-139">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a3697-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
