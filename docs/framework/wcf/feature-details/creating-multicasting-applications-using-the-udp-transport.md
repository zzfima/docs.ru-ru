---
title: Создание приложений многоадресной рассылки с помощью транспорта определяемой пользователем функции
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: 6825aaafe87ae362fd9266f7c7a82a36d054a69f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185244"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a>Создание приложений многоадресной рассылки с помощью транспорта определяемой пользователем функции
Приложения многоадресной рассылки одновременно отправляют маленькие сообщения большому количеству получателей без необходимости установления прямого соединения. Подобные приложения прежде всего ориентируются на скорость выполнения, а не надежность. Другими словами, отправка данных точно в срок важнее обеспечения доставки конкретного сообщения. WCF теперь поддерживает создание приложений многоадресной рассылки с помощью <xref:System.ServiceModel.UdpBinding>. Этот транспорт может оказаться полезным в случаях, когда служба должна одновременно отправлять маленькие сообщения множеству клиентов. Пример подобной службы - приложение, работающее с биржевыми сводками.  
  
## <a name="implementing-a-multicast-application"></a>Реализация приложения многоадресной рассылки  
 Чтобы реализовать приложение многоадресной рассылки, определите контракт службы и реализуйте контракт службы для каждого программного компонента, который должен отвечать на сообщения многоадресной рассылки. Например, приложение для работы с биржевыми сводками может определить такой контракт:  
  
```csharp
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 Каждое приложение, которому нужно получать сообщения многоадресной рассылки, должно разместить службу, реализующую данный интерфейс.  Ниже представлен образец кода, демонстрирующий получение сообщений многоадресной рассылки:  
  
```csharp
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 Приложение задает UDP-адрес, который будут прослушивать все службы. Создается новый объект <xref:System.ServiceModel.ServiceHost> и предоставляется конечная точка службы с помощью <xref:System.ServiceModel.UdpBinding>. Затем открывается <xref:System.ServiceModel.ServiceHost> и начинает прослушивание в ожидании входящих сообщений.  
  
 В подобном варианте работы приложения клиент отправляет сообщения многоадресной рассылки. Сообщения многоадресной рассылки получит каждая служба, прослушивающая правильный UDP-адрес. Ниже приведен пример клиента, который отправляет сообщения многоадресной рассылки.  
  
```csharp
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine($"sent stock info at {DateTime.Now}");
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 Данный код создает сводку биржевых данных, а затем использует контракт службы IStockTicker для многоадресной отправки сообщений и вызова служб, слушающих определенный UDP-адрес.  
  
### <a name="udp-and-reliable-messaging"></a>Протокол UDP и надежный обмен сообщениями  
 Привязка к UDP-протоколу не обеспечивает надежный обмен сообщениями из-за особенностей самого протокола UDP. Если необходимо подтвердить получение сообщений удаленной конечной точкой, используйте транспорт, поддерживающий надежный обмен сообщениями, например протокол HTTP или TCP. Для получения дополнительной информации о надежных сообщений см.https://go.microsoft.com/fwlink/?LinkId=231830  
  
### <a name="two-way-multicast-messaging"></a>Двусторонняя многоадресная отправка сообщений  
 Хотя сообщения многоадресной рассылки обычно отправляются в одну сторону, транспорт UdpBinding поддерживает обмен сообщениями в режиме «запрос-ответ». Сообщения, отправленные с помощью транспорта UDP, содержат адреса отправителя и получателя. Следует соблюдать предосторожность при использовании адреса отправителя, так как он может быть изменен злоумышленниками в ходе доставки сообщения.  Адрес можно проверить с помощью следующего кода:  
  
```csharp
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 Данный код проверяет первый байт из адреса отправителя, чтобы определить, содержит ли он байт 0xE0, который означает, что это адрес многоадресной рассылки.  
  
### <a name="security-considerations"></a>Соображения безопасности  
 При прослушивании сообщений многоадресной рассылки маршрутизатору отправляется ICMP-пакет, извещающий его о прослушивании адреса многоадресной рассылки. Любой пользователь локальной подсети, имеющий соответствующие разрешения, может прослушивать пакеты подобных типов и определять прослушиваемый адрес и порт и многоадресной рассылки.  
  
 Не используйте IP-адрес отправителя по соображениям безопасности. Возможна фальсификация этой информации, и приложение может начать отправлять ответы другому компьютеру. Включение безопасности на уровне сообщения позволяет устранить подобную угрозу. На уровне сети используйте протокол IPSec (Internet Protocol Security) или NAP (Network Access Protection).
