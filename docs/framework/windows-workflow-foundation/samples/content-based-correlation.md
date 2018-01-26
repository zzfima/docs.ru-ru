---
title: "Корреляция по содержимому"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971636df3393adda96dff779c1533969f67bf57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="content-based-correlation"></a>Корреляция по содержимому
В этом образце демонстрируется, как действия по обмену сообщениями (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, и <xref:System.ServiceModel.Activities.ReceiveReply>) могут использоваться с несколькими корреляциями на основе содержимого, и одной корреляцией на основе содержимого. В этом сценарии корреляция сначала запускается на основе идентификатора заказа на покупку, затем создается другая корреляция на основе идентификатора клиента. Это показывает, как действие <xref:System.ServiceModel.Activities.Receive> может как следовать существующей корреляции, так и запускать новую корреляцию на основе одного и того же входящего сообщения.  
  
## <a name="demonstrates"></a>Демонстрации  
 Действия обмена сообщениями и корреляция на основе содержимого.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано использование нескольких корреляции на основе содержимого.  В этом сценарии корреляция сначала запускается на основе идентификатора заказа на покупку, затем создается другая корреляция на основе идентификатора клиента.  Корреляции каскадно выводятся действием <xref:System.ServiceModel.Activities.Receive>, которое как следует существующей корреляции (идентификатора заказа на покупку), так и запускает новую корреляцию (идентификатор клиента) на основе одного и того же входящего сообщения.  Для осуществления этого действие <xref:System.ServiceModel.Activities.Receive> использует свойства <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> и <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.  
  
2.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения CascadingCorrelation.sln.  
  
3.  Для построения решения нажмите CTRL+SHIFT+B.  
  
4.  Для запуска сервера нажмите F5.  
  
5.  После того как служба готова к прослушиванию сообщений, щелкните правой кнопкой мыши проект «Клиент» в обозревателе решений и запустите его.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`