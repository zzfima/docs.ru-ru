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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bfedfbd0177018de4affce67f16ee5f713f7d5de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="best-practices-intermediaries"></a>Рекомендации по использованию: посредники
Следует уделять особое внимание к ошибкам при вызове посредников, чтобы убедиться, что каналы на стороне службы посредника закрыты правильно.  
  
 Рассмотрим следующий сценарий. Клиент вызывает метод в посреднике, который затем вызывает внутреннюю службу.  Внутренняя служба не определяет контракт ошибок, поэтому любая ошибка данной службы будет обрабатываться как нетипизированная ошибка.  Внутренняя служба вызывает <xref:System.ApplicationException> и WCF правильно прерывает канал на стороне службы. Затем <xref:System.ApplicationException> появляется как <xref:System.ServiceModel.FaultException>, которое пробрасывается дальше к посреднику. Посредник повторно пробрасывает <xref:System.ApplicationException>. WCF интерпретирует ее как нетипизированную ошибку из посредника и перенаправляет ее клиенту. При получении ошибки и посредник и клиент закрывают каналы на своей стороне. Канал на стороне службы посредника при этом остается открытым, поскольку WCF не знает, является ли ошибка неустранимой.  
  
 В этом случае рекомендуется определять, является ли ошибка от службы неустранимой, и, если да, посредник должен вызвать сбой канала на стороне службы, как показано в следующем фрагменте кода.  
  
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
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок WCF](../../../docs/framework/wcf/wcf-error-handling.md)  
 [Указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
