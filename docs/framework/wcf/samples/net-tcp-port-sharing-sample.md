---
title: Пример совместного использования портов Net.TCP
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: ac90a50c6fe06a643881da2889fdea308404508e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144296"
---
# <a name="nettcp-port-sharing-sample"></a>Пример совместного использования портов Net.TCP
Протокол TCP/IP использует 16-разрядное число, называемое номером порта, чтобы различать подключения к разным сетевым приложениям, выполняющимся на одном компьютере. Если приложение ожидает передачи данных через порт, то весь трафик TCP через этот порт перенаправляется данному приложению. Другие приложения не могут одновременно ожидать передачи данных через тот же порт.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 У многих протоколов имеется номер порта по умолчанию. Например, для протокола HTTP обычно используется порт TCP 80. У служб IIS имеется прослушиватель для совместного использования одного порта несколькими приложениями HTTP. Службы IIS ожидают передачи данных непосредственно через этот порт и перенаправляют сообщения соответствующим приложениям в зависимости от информации внутри сообщения. Это позволяет нескольким приложениям HTTP использовать один и тот же номер порта, не конкурируя за порт для получения сообщений.  
  
 NetTcp Port Sharing — это функция Фонда коммуникаций Windows (WCF), которая аналогичным образом позволяет нескольким сетевым приложениям совместно использовать один порт. Служба общего доступа к портам NetTcp принимает подключения с помощью протокола net.tcp и перенаправляет сообщения в зависимости от их адреса назначения.  
  
 По умолчанию служба общего доступа к портам NetTcp отключена. Перед запуском этого образца необходимо вручную включить эту службу. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md) Если служба отключена, при запуске серверного приложения создается исключение.  
  
```console
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 Общий доступ к портам включается на сервере путем задания свойства <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> привязки <xref:System.ServiceModel.NetTcpBinding> или элемента привязки <xref:System.ServiceModel.Channels.TcpTransportBindingElement>. Чтобы использовать на сервере общий доступ к портам, клиенту не требуются сведения о его конфигурации.  
  
## <a name="enabling-port-sharing"></a>Включение общего доступа к портам  
 В следующем примере кода показано, как включить на сервере общий доступ к портам. Он запускает экземпляр службы `ICalculator` на фиксированном порту со случайным путем универсального кода ресурса (URI). Хотя две службы могут использовать один и тот же порт, их адреса конечных точек должны быть уникальными, чтобы служба общего доступа к портам NetTcp могла перенаправлять сообщения нужным приложениям.  

```csharp
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address = $"net.tcp://localhost:9000/calculator/{salt}";
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```

 Если общий доступ к портам включен, службу можно запускать несколько раз без конфликта по поводу номера порта. Если изменить код и отключить общий доступ к портам, то в случае запуска двух экземпляров службы при запуске второго экземпляра будет создано исключение <xref:System.ServiceModel.AddressAlreadyInUseException>.  
  
```console  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a>Запуск примера  
 Чтобы проверить, что сообщения правильно направляются службам, которые совместно используют порт, можно воспользоваться тестовым клиентом.  

```csharp
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = $"net.tcp://localhost:9000/calculator/{salt}";
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```

 Каждый экземпляр службы выводит собственный уникальный номер и адрес. Например, при запуске файла service.exe можно увидеть следующий текст.  
  
```console  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 При запуске файла client.exe введите показанный номер службы.  
  
```console  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 Этот образец можно выполнять на нескольких компьютерах, если изменить созданный адрес, используемый клиентом. В файле Client.cs измените строку формата адреса конечной точки, чтобы она соответствовало новому адресу службы. Замените вхождения localhost на IP-адрес серверного компьютера. После внесения этого изменения необходимо перекомпилировать пример.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Установите ASP.NET 4.0 с помощью следующей команды.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
3. Включите службу общего доступа к портам NetTcp, как описано в начале раздела.  
  
4. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md) Конкретные сведения о выполнении этого образца описаны в разделе "Выполнение образца".  
