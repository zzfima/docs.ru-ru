---
title: Общие сведения о размещении служб рабочих процессов
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: 7b5de31b5931af13b41b11af6e48a52b5628e27c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489564"
---
# <a name="hosting-workflow-services-overview"></a>Общие сведения о размещении служб рабочих процессов
Для выполнения служб рабочего процесса они должны быть размещены. Класс <xref:System.ServiceModel.WorkflowServiceHost> представляет собой готовый узел размещения рабочих процессов, поддерживающий использование нескольких экземпляров, настройку и обмен сообщениями WCF (хотя от размещаемых рабочих процессов и не требуется обмена сообщениями).  Он также реализует сохраняемость, отслеживание и контроль за экземплярами через набор поведений службы.  Как и класс WCF <xref:System.ServiceModel.ServiceHost>, класс <xref:System.ServiceModel.WorkflowServiceHost> может быть резидентным в любом управляемом приложении .NET или размещаться на веб-сервере IIS / WAS (в виде файла XAMLX).  В этом разделе описано размещение службы рабочего процесса.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Размещение служб рабочих процессов](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 Описывает размещение служб рабочего процесса.  
  
 [Внутренние особенности размещения службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 Описывает, как объект <xref:System.ServiceModel.WorkflowServiceHost> обрабатывает входящие сообщения.  
  
 [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 Описывает способы расширения функциональности узла службы рабочего процесса.  
  
 [Конечная точка элемента управления рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 Описывает, как определить конечную точку, позволяющую создавать экземпляры рабочих процессов.  
  
 [Практическое руководство. Размещение не являющегося службой рабочего процесса в службах IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 Демонстрирует размещение в службах IIS рабочего процесса, который не является службой рабочего процесса.  
  
 [Практическое руководство. Размещение службы рабочего процесса с помощью Windows Server App Fabric](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
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
