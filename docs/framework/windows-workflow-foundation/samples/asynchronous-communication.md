---
title: Асинхронное взаимодействие
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e85f7efb0de1326ceb5091c305b20f34809eab57
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45557802"
---
# <a name="asynchronous-communication"></a>Асинхронное взаимодействие
В этом примере демонстрируется, как обмен данными между двумя отдельными службами Windows Workflow Foundation (WF) происходит в асинхронном режиме по умолчанию.  
  
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
  
2.  В **общие свойства**выберите **запускаемым проектом**и выберите **несколько запускаемых проектов**.  
  
3.  Переместить **RentalApprovalService** в первую позицию в списке, за которым следует **CreditCheckService**, за которым следует **клиента**. Задайте **запустить** действие для всех трех проектов.  
  
4.  Нажмите кнопку **ОК**, и нажмите клавишу F5 для запуска примера.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
