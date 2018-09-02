---
title: Расширенная обработка ошибок
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 72fb9885408759f5781501b548f81625d258d13c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423436"
---
# <a name="advanced-error-handling"></a>Расширенная обработка ошибок
В этом примере демонстрируется служба маршрутизации Windows Communication Foundation (WCF). Служба маршрутизации является компонентом WCF, который упрощает Включение маршрутизатора на основе содержимого в приложении. В этом образце показано, как служба маршрутизации выполняет интеллектуальное восстановление работы после ошибок с использованием транзакций и более сложных понятий обмена сообщениями, таких как многоадресная передача.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В этом образце служба маршрутизации настраивается для считывания сообщения из очереди MSMQ и многоадресной передачи этого сообщения в два списка очередей. Один список используется для очередей обслуживания, а другой - для очередей журнала.  
  
 Поскольку по умолчанию привязка MSMQ, которая используется службой маршрутизации, поддерживает использование транзакций, служба маршрутизации проверяет, что сообщение входит в транзакцию и принято хотя бы одной очередью из каждого списка, а затем сообщает очереди входящих сообщений (`InQ`) об успешной маршрутизации сообщения. Поэтому в случае, когда обе очереди службы обслуживания или обе очереди журнала становятся недоступны, служба маршрутизации сообщает, что не удалось выполнить маршрутизацию сообщения, и очередь входящих сообщений должна выполнить какое-либо действие. Это действие заключается в перемещении сообщения в системную очередь недоставленных сообщений.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  > [!IMPORTANT]
    >  Перед запуском этого образца установите очередь MSMQ. Если очередь MSMQ не установлена, то при запуске образца возвращается сообщение исключения. Инструкции по установке MSMQ можно найти в [Установка очереди сообщений (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).  
  
     Откройте файл AdvancedErrorHandling.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Нажмите клавишу **F5** или **CTRL + SHIFT + B** в Visual Studio.  
  
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
 [Образцы размещения AppFabric и сохраняемости](https://go.microsoft.com/fwlink/?LinkId=193961)
