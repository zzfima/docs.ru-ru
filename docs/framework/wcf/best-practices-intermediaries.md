---
title: "Рекомендации по использованию: посредники"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3185761ef784051c7508c3684d46997521483f04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="b7292-102">Рекомендации по использованию: посредники</span><span class="sxs-lookup"><span data-stu-id="b7292-102">Best Practices: Intermediaries</span></span>
<span data-ttu-id="b7292-103">Следует уделять особое внимание к ошибкам при вызове посредников, чтобы убедиться, что каналы на стороне службы посредника закрыты правильно.</span><span class="sxs-lookup"><span data-stu-id="b7292-103">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="b7292-104">Рассмотрим следующий сценарий.</span><span class="sxs-lookup"><span data-stu-id="b7292-104">Consider the following scenario.</span></span> <span data-ttu-id="b7292-105">Клиент вызывает метод в посреднике, который затем вызывает внутреннюю службу.</span><span class="sxs-lookup"><span data-stu-id="b7292-105">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="b7292-106">Внутренняя служба не определяет контракт ошибок, поэтому любая ошибка данной службы будет обрабатываться как нетипизированная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b7292-106">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="b7292-107">Внутренняя служба вызывает <xref:System.ApplicationException> и WCF правильно прерывает канал на стороне службы.</span><span class="sxs-lookup"><span data-stu-id="b7292-107">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="b7292-108">Затем <xref:System.ApplicationException> появляется как <xref:System.ServiceModel.FaultException>, которое пробрасывается дальше к посреднику.</span><span class="sxs-lookup"><span data-stu-id="b7292-108">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="b7292-109">Посредник повторно пробрасывает <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="b7292-109">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="b7292-110">WCF интерпретирует ее как нетипизированную ошибку из посредника и перенаправляет ее клиенту.</span><span class="sxs-lookup"><span data-stu-id="b7292-110">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="b7292-111">При получении ошибки и посредник и клиент закрывают каналы на своей стороне.</span><span class="sxs-lookup"><span data-stu-id="b7292-111">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="b7292-112">Канал на стороне службы посредника при этом остается открытым, поскольку WCF не знает, является ли ошибка неустранимой.</span><span class="sxs-lookup"><span data-stu-id="b7292-112">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="b7292-113">В этом случае рекомендуется определять, является ли ошибка от службы неустранимой, и, если да, посредник должен вызвать сбой канала на стороне службы, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="b7292-113">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    Else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7292-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b7292-114">See Also</span></span>  
 [<span data-ttu-id="b7292-115">Обработка ошибок WCF</span><span class="sxs-lookup"><span data-stu-id="b7292-115">WCF Error Handling</span></span>](../../../docs/framework/wcf/wcf-error-handling.md)  
 [<span data-ttu-id="b7292-116">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="b7292-116">Specifying and Handling Faults in Contracts and Services</span></span>](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
