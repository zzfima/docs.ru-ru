---
title: "Расширенная обработка ошибок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7771b9a4d5a6c0fb4349894afd348e9dece27fd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-error-handling"></a>Расширенная обработка ошибок
В этом образце показана служба маршрутизации [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Служба маршрутизации - это компонент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который упрощает включение маршрутизатора на основе содержимого в приложение. В этом образце показано, как служба маршрутизации выполняет интеллектуальное восстановление работы после ошибок с использованием транзакций и более сложных понятий обмена сообщениями, таких как многоадресная передача.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В этом образце служба маршрутизации настраивается для считывания сообщения из очереди MSMQ и многоадресной передачи этого сообщения в два списка очередей. Один список используется для очередей обслуживания, а другой - для очередей журнала.  
  
 Поскольку по умолчанию привязка MSMQ, которая используется службой маршрутизации, поддерживает использование транзакций, служба маршрутизации проверяет, что сообщение входит в транзакцию и принято хотя бы одной очередью из каждого списка, а затем сообщает очереди входящих сообщений (`InQ`) об успешной маршрутизации сообщения. Поэтому в случае, когда обе очереди службы обслуживания или обе очереди журнала становятся недоступны, служба маршрутизации сообщает, что не удалось выполнить маршрутизацию сообщения, и очередь входящих сообщений должна выполнить какое-либо действие. Это действие заключается в перемещении сообщения в системную очередь недоставленных сообщений.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  > [!IMPORTANT]
    >  Перед запуском этого образца установите очередь MSMQ. Если очередь MSMQ не установлена, то при запуске образца возвращается сообщение исключения. Инструкции по установке MSMQ можно найти в [Установка Message Queuing (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).  
  
     Откройте файл AdvancedErrorHandling.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Нажмите клавишу **F5** или **CTRL + SHIFT + B** в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
    1.  Если приложение построено с помощью нажатия клавиш CTRL+SHIFT+B, его необходимо запустить из файла ./RoutingService/bin/debug/RoutingService.exe.  
  
3.  Чтобы запустить клиент, нажмите клавишу ВВОД в окне консоли.  
  
4.  В каждом случае клиент возвращает разную статистику об очередях.  
  
    1.  Далее представлены данные, возвращаемые для случая 1 (без ошибок).  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  Далее представлены данные, возвращаемые для случая 3 (ошибки в основной очереди и очереди журнала).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  Далее представлены данные, возвращаемые для случая 4 (ошибки в основной очереди обслуживания, а также в основной и резервной очередях журнала).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  Далее представлены данные, возвращаемые для случая 2 (ошибка в основной очереди обслуживания).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a>Настраивается в коде или в файле App.config  
 В поставляемой конфигурации образца поведение маршрутизатора определяется в файле App.config. Кроме того, можно изменить имя файла RoutingService\App.config, чтобы он не распознавался, и изменить значение поля `configDriven` в файле RoutingService\Program.cs на `false`, чтобы использовать конфигурацию, определенную в коде. Поведение маршрутизатора будет одинаковым для обоих методов.  
  
### <a name="scenario"></a>Сценарий  
 В этом образце показано, что служба маршрутизации обладает расширенными возможностями по обработки сообщений. В частности, поддерживаются транзакции и контекст получения. Эти возможности применяются для верной обработки ошибок.  
  
### <a name="real-world-scenario"></a>Реальный сценарий  
 Компания Contoso планирует транзакционные операции получения сообщений в службе маршрутизации, чтобы обеспечить доставку данных во всех необходимые службы даже при возникновении ошибок. Кроме того, требуется правильная автоматическая обработка ошибок и отправка предупреждения в случае, когда сообщение не удается доставить даже путем применения логики обработки ошибок. Для этого в службе маршрутизации настраивается резервное переключение на специальные конечные точки, и служба маршрутизации обрабатывает ошибки. В этом процессе выполняется создание, завершение, откат и прерывание транзакций и контекстов получения по мере необходимости.  
  
## <a name="see-also"></a>См. также  
 [Образцы размещения и сохраняемости образцы](http://go.microsoft.com/fwlink/?LinkId=193961)
