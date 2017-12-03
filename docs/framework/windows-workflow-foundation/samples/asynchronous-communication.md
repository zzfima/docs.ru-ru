---
title: "Асинхронное взаимодействие"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea2d705a38ddae1689d212bbd50196920fe73fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="asynchronous-communication"></a>Асинхронное взаимодействие
В этом образце показано взаимодействие между двумя разными службами [!INCLUDE[wf](../../../../includes/wf-md.md)], проходящее по умолчанию в асинхронном режиме.  
  
## <a name="demonstrates"></a>Демонстрации  
 Асинхронное взаимодействие между службами [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано асинхронное взаимодействие между приложениями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] с помощью действий отправки и получения сообщений, предоставляемых .NET Framework.  
  
 Данный образец состоит из следующих трех проектов.  
  
 CreditCheckService  
 Эта служба получает кредитную историю определенного лица или стоимость приобретаемого товара и принимает решение, следует ли предоставить этому лицу кредит.  
  
 RentalApprovalService  
 Эта служба получает заявление от лица, которому требуется кредит. Эта служба взаимодействует в асинхронном режиме со службой `CreditCheckService` для принятия решения об одобрении заявки на кредит.  
  
 Клиент  
 Клиент связывается в синхронном режиме со службой `RentalApprovalService`, чтобы узнать, одобрено ли заявление на получение кредита.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Щелкните правой кнопкой мыши **AsynchronousCommunication** решение, выберите команду **свойства**.  
  
2.  В **общие свойства**выберите **запускаемый проект**и выберите **несколько запускаемых проектов**.  
  
3.  Переместить **RentalApprovalService** в первую позицию в списке, за которым следует **CreditCheckService**, за которым следует **клиента**. Задать **запустить** действие для всех трех проектов.  
  
4.  Нажмите кнопку **ОК**, и нажмите клавишу F5 для запуска примера.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
