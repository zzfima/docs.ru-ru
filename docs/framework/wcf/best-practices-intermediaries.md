---
title: "Правила и рекомендации: Посредники | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Правила и рекомендации: Посредники
Следует проявлять особое внимание к правильной обработке ошибок при вызове посредников, чтобы убедиться, что каналы на стороне службы в посреднике закрыты правильно.  
  
 Рассмотрим следующий скрипт.Клиент вызывает посредника, который затем вызывает внутреннюю службу.Внутренняя служба не определяет контракт сбоя, поэтому любая ошибка данной службы будет обрабатываться как нетипизированная ошибка.Внутренняя служба вызывает <xref:System.ApplicationException> и WCF правильно прерывает канал на стороне службы.Затем <xref:System.ApplicationException> перехватывает <xref:System.ServiceModel.FaultException>, вызываемое посредником.Посредник повторно вызывает <xref:System.ApplicationException>.WCF интерпретирует это как автоматическую типизированную ошибку от посредника и перенаправляет его в клиент.При получении ошибки посредник и клиент вызывают сбой каналов со стороны клиента.Канал на стороне службы посредника при этом остается открытым, поскольку WCF не знает, что ошибка неустранима.  
  
 В этом случае рекомендуется определять, является ли ошибка, поступающая от службы, неустранимой, и если да, посредник должен вызвать сбой канала на стороне службы, как показано в следующем фрагменте кода.  
  
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
  
## См. также  
 [Обработка ошибок WCF](../../../docs/framework/wcf/wcf-error-handling.md)   
 [Задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)