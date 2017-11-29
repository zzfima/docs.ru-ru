---
title: "Метаданные CustomDiscoveryMetadata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5b3272b642a04821d8343cae776e48f90d266cfe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="customdiscoverymetadata"></a>Метаданные CustomDiscoveryMetadata
В этом образце показано, как вставить пользовательские метаданные XML в метаданные обнаружения для конечной точки, которая предоставляется службой и поддерживает обнаружение. Затем в образце показано, как клиент может найти службу и извлечь эти пользовательские данные. Этот образец состоит из двух проектов: служба и клиент.  
  
## <a name="service"></a>Служба  
 В методе `main` образца показано, что объект типа <xref:System.Xml.Linq.XElement> заполняется нужными полями и добавляется в объект <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>. Этот объект <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> добавляется в определенную конечную точку. Когда выполняется обнаружение этой конечной точки, метаданные обнаружения содержат пользовательские данные, добавленные здесь.  
  
## <a name="client"></a>Клиент  
 В образце показано, как метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> вызывается в объекте <xref:System.ServiceModel.Discovery.DiscoveryClient>. Затем в результирующем объекте <xref:System.ServiceModel.Discovery.FindResponse> запрашиваются подходящие и ожидаемые XML-элементы. Затем эти элементы выводятся на консоль.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Загрузите решение проекта в среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и постройте проект.  
  
2.  Сначала запустите приложение службы, созданное в каталоге [основной каталог решения]\service\bin\debug, а затем запустите клиентское приложение, созданное в папке [основной каталог решения]\Client\bin\debug  
  
3.  Заметьте, что служба становится доступной, клиент находит службу и выводит метаданные, опубликованные в конечной точке.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a>См. также
