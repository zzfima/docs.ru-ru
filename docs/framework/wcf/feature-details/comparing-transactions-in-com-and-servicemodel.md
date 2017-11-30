---
title: "Сравнение транзакций в COM+ и ServiceModel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 712f8a7a153d7255275ff7ebaa647d5a624f8ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="82da6-102">Сравнение транзакций в COM+ и ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82da6-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="82da6-103">В этом разделе описывается, как моделировать поведение транзакционной службы COM+ с помощью атрибутов [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] пространства имен <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="82da6-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="82da6-104">Эмуляция COM+ с помощью атрибутов ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82da6-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="82da6-105">В следующей таблице сравнивается перечисление <xref:System.EnterpriseServices.TransactionOption>, используемое для создания транзакции `EnterpriseServices`, и их корреляция с атрибутами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в пространстве имен <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="82da6-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="82da6-106">Атрибут COM+</span><span class="sxs-lookup"><span data-stu-id="82da6-106">COM+ attribute</span></span>|<span data-ttu-id="82da6-107">Атрибуты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82da6-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="82da6-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="82da6-108">RequiresNew</span></span>|<span data-ttu-id="82da6-109">Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span><span class="sxs-lookup"><span data-stu-id="82da6-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="82da6-110">Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="82da6-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="82da6-111">Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="82da6-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="82da6-112">Обязательно</span><span class="sxs-lookup"><span data-stu-id="82da6-112">Required</span></span>|<span data-ttu-id="82da6-113">Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span><span class="sxs-lookup"><span data-stu-id="82da6-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="82da6-114">Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="82da6-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="82da6-115">Атрибут `TransactionFlow` в элементе привязки имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="82da6-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="82da6-116">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="82da6-116">Supported</span></span>|<span data-ttu-id="82da6-117">Прямого эквивалента не существует.</span><span class="sxs-lookup"><span data-stu-id="82da6-117">There is no direct equivalent.</span></span> <span data-ttu-id="82da6-118">В общем случае необходимо принимать поведение, заданное для `Required`.</span><span class="sxs-lookup"><span data-stu-id="82da6-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="82da6-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="82da6-119">NotSupported</span></span>|<span data-ttu-id="82da6-120">Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="82da6-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="82da6-121">Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="82da6-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="82da6-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="82da6-122">Disabled</span></span>|<span data-ttu-id="82da6-123">Прямого эквивалента не существует.</span><span class="sxs-lookup"><span data-stu-id="82da6-123">There is no direct equivalent.</span></span> <span data-ttu-id="82da6-124">В общем случае необходимо принимать поведение, заданное для `NotSupported`.</span><span class="sxs-lookup"><span data-stu-id="82da6-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
