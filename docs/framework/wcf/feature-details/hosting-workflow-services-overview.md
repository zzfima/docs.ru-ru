---
title: "Общие сведения о размещении служб рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a>Общие сведения о размещении служб рабочих процессов
Для выполнения служб рабочего процесса они должны быть размещены. Класс <xref:System.ServiceModel.WorkflowServiceHost> представляет собой готовый узел размещения рабочих процессов, поддерживающий использование нескольких экземпляров, настройку и обмен сообщениями WCF (хотя от размещаемых рабочих процессов и не требуется обмена сообщениями).  Он также реализует сохраняемость, отслеживание и контроль за экземплярами через набор поведений службы.  Как и класс WCF <xref:System.ServiceModel.ServiceHost>, класс <xref:System.ServiceModel.WorkflowServiceHost> может быть резидентным в любом управляемом приложении .NET или размещаться на веб-сервере IIS / WAS (в виде файла XAMLX).  В этом разделе описано размещение службы рабочего процесса.  
  
## <a name="in-this-section"></a>Содержание  
 [Размещение служб рабочего процесса](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 Описывает размещение служб рабочего процесса.  
  
 [Внутренние особенности размещения службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 Описывает, как объект <xref:System.ServiceModel.WorkflowServiceHost> обрабатывает входящие сообщения.  
  
 [Расширяемость узла службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 Описывает способы расширения функциональности узла службы рабочего процесса.  
  
 [Конечная точка управления рабочим процессом](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 Описывает, как определить конечную точку, позволяющую создавать экземпляры рабочих процессов.  
  
 [Как: разместить не являющийся службой рабочий процесс в службах IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 Демонстрирует размещение в службах IIS рабочего процесса, который не является службой рабочего процесса.  
  
 [Как: размещение службы рабочего процесса с помощью Windows Server App Fabric](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 Демонстрирует размещение существующей службы рабочего процесса в фабрике приложений Windows Server.  
  
 [Настройка WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 Описывает управление сохраняемостью, отслеживанием, простоем и поведением необработанных исключений.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)
