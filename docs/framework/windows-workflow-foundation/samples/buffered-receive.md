---
title: Прием через буфер
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: ee53edafc94fd5efd4e412b1b9198a8763b79462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518715"
---
# <a name="buffered-receive"></a>Прием через буфер
В этом примере показано, как настроить и сконфигурировать функцию буфера получения в Windows Workflow Foundation (WF). Функция буфера получения позволяет автору рабочего процесса создавать рабочий процесс, не заботясь о том, в каком порядке получаются сообщения. Возможность буфера получения осуществляет буферизацию сообщений на локальном уровне и доставляет их, как только рабочий процесс готов к их получению.  
  
## <a name="demonstrates"></a>Демонстрации  
 Обработка внеочередных сообщений с использованием функции буфера получения сообщений.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце службы Windows Communication Foundation (WCF) реализуется с помощью [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и последовательность <xref:System.ServiceModel.Activities.Receive> действий. Данный рабочий процесс моделирует простой процесс утверждения заявок на получение кредита. Рабочий процесс предполагает утверждение трех уведомлений на получение кредита. Windows Communication Foundation (WCF) клиентское приложение отправляет три связанных между собой уведомления в порядке, обратном ожидает служба. Поскольку возможность буфера получения в этой службе включена, любое внеочередное сообщение помещается в буфер службы и будет обработано, как только рабочий процесс будет готов к его получению.  
  
 Поскольку функция буфера получения требует поддержки <xref:System.ServiceModel.Activities.ReceiveContent> через привязку, в ней используется <xref:System.ServiceModel.NetMsmqBinding>. Привязка не требует специальной настройки, поэтому используются значения по умолчанию.  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 Служба также предоставляет метаданные службы, используя для этого <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
 Конечная точка клиента настраивается аналогично, с использованием <xref:System.ServiceModel.NetMsmqBinding>. Код клиента и его конфигурация формируются с помощью **добавить ссылку на службу** возможности Visual Studio. В следующем примере в файле App.config формируется конечная точка клиента.  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 Для этого образца необходимо включить следующие компоненты Windows.  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Совместимость управления, метабаза и совместимость конфигурации  
  
3.  Службы Интернета, компоненты разработки приложений и ASP.NET  
  
4.  Сервер очереди сообщений (Майкрософт) (MSMQ)  
  
#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца  
  
1.  Находясь в командной строке [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], зарегистрируйте ASP.NET, введя команду `aspnet_regiis –I`, затем нажмите клавишу ВВОД.  
  
2.  Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] от имени администратора.  
  
3.  Откройте LoanService.sln.  
  
4.  При появлении запроса, если вы хотите создать виртуальные каталоги для проекта LoanService, выберите **Да**.  
  
#### <a name="to-set-up-the-service-queues"></a>Настройка очередей обслуживания  
  
1.  Нажмите клавишу F5 для запуска приложения LoanClient, создающего очереди и активирующего службы, определенные в Service1.xamlx.  
  
2.  Откройте **Управление компьютером** консоли, выполнив команду Compmgmt.msc из командной строки.  
  
3.  В **Управление компьютером** консоли, разверните **службы**, **приложений**, **очереди сообщений**, **частные очереди** .  
  
4.  Щелкните правой кнопкой мыши очередь loanservice/service1.xamlx и выберите **свойства**.  
  
5.  Выберите **безопасности** и добавьте **сообщение получают все**, **Просмотр сообщения** и **Отправка сообщения** разрешения.  
  
6.  Откройте диспетчер служб [!INCLUDE[iis60](../../../../includes/iis60-md.md)].  
  
7.  Перейдите к **сервера**, **сайтов**, **по умолчанию веб-сайт**, **закрытый**, **LoanService** и выберите  **Дополнительные параметры**  
  
8.  Изменение **включенные протоколы** быть **http**, **net.msmq**.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Перейдите к http://localhost/private/loanservice/service1.xamlx чтобы убедиться, что служба запущена.  
  
2.  Нажмите клавишу F5, чтобы запустить приложение LoanClient. После завершения рабочего процесса в папке C:\Inbox должен быть сохранен файл out.txt с результатом обмена сообщениями.  
  
#### <a name="to-clean-up"></a>Очистка  
  
1.  Откройте **Управление компьютером** консоли, выполнив команду Compmgmt.msc из командной строки.  
  
2.  Разверните **службы** и **приложений**, **очереди сообщений**, **частные очереди**.  
  
3.  Удалите очередь loanservice/service1.xamlx.  
  
4.  Удалите каталог C:\Inbox.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
