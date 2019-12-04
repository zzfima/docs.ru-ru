---
title: Пользовательский перехватчик сообщений
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 53005212bc834d73ab5cbb4545d1477112f29c75
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716816"
---
# <a name="custom-message-interceptor"></a>Пользовательский перехватчик сообщений
Данный образец демонстрирует использование модели расширяемости канала. В частности, показано, как реализовать пользовательский элемент привязки, который создает фабрики и прослушиватели каналов для перехвата всех входящих и исходящих сообщений в определенной точке стека времени выполнения. В состав образца входят клиент и сервер, которые демонстрируют использование этих пользовательских фабрик.  
  
 В этом образце служба и клиент являются консольными программами (EXE). Как клиент, так и служба используют общую библиотеку (DLL), которая содержит пользовательский элемент привязки и ассоциированные с ним объекты времени выполнения.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 В этом примере описывается рекомендуемая процедура создания пользовательского многоуровневого канала в Windows Communication Foundation (WCF) с помощью платформы Channel и следующих рекомендаций по WCF. Чтобы создать пользовательский многоуровневый канал, выполните следующие действия.  
  
1. Выберите формы канала, которые будут поддерживать фабрика и прослушиватель каналов.  
  
2. Создайте фабрику и прослушиватель каналов, которые поддерживают выбранную форму канала.  
  
3. Присоедините элемент привязки, добавляющий пользовательский многоуровневый канал в стек каналов.  
  
4. Добавьте раздел расширения элементов привязки, чтобы представить новый элемент привязки системе конфигурации.  
  
## <a name="channel-shapes"></a>Формы каналов  
 При создании пользовательского многоуровневого канала в первую очередь необходимо решить, какие формы требуются для канала. Данным инспектором сообщений поддерживается любая форма, поддерживаемая уровнем ниже (например, если уровень ниже может выполнить построение метода <xref:System.ServiceModel.Channels.IOutputChannel> и интерфейса <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, то также предоставляется метод <xref:System.ServiceModel.Channels.IOutputChannel> и интерфейс <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).  
  
## <a name="channel-factory-and-listener-factory"></a>Фабрика и прослушиватель каналов  
 Следующий шаг создания пользовательского многоуровневого канала - реализация интерфейса <xref:System.ServiceModel.Channels.IChannelFactory> для каналов клиентов и интерфейса <xref:System.ServiceModel.Channels.IChannelListener> для каналов служб.  
  
 Эти классы получают внутреннюю фабрику и прослушиватель и делегируют все вызовы внутренней фабрике и прослушивателю, кроме `OnCreateChannel` и `OnAcceptChannel`.  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{ 
    //... 
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{ 
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a>Добавление элемента привязки  
 В образце определен пользовательский элемент привязки: `InterceptingBindingElement`. `InterceptingBindingElement` принимает `ChannelMessageInterceptor` в качестве входных данных и использует эту `ChannelMessageInterceptor` для обработки сообщений, которые проходят через него. Только этот класс должен быть открытым. Фабрика, прослушиватель и каналы - все они могут являться внутренними реализациями открытых интерфейсов времени выполнения.  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a>Добавление поддержки конфигурации  
 Для интеграции с конфигурацией привязки библиотека определяет обработчик раздела конфигурации в качестве раздела расширения элемента привязки. Файлы конфигурации клиента и сервера должны зарегистрировать расширение элемента привязки в системе конфигурации. Реализации, требующие предоставить их элементы привязки в системе конфигурации, могут наследовать от этого класса.  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement 
{ 
    //... 
}
```  
  
## <a name="adding-policy"></a>Добавление политики  
 Для интеграции с системой политики `InterceptingBindingElement` реализует расширение IPolicyExportExtension, чтобы сообщить об участии в создании политики. Чтобы поддержать импорт политики на созданном клиенте, пользователь может зарегистрировать производный класс `InterceptingBindingElementImporter` и переопределить `CreateMessageInterceptor`(), чтобы создать принадлежащий им класс `ChannelMessageInterceptor` с разрешенной политикой.  
  
## <a name="example-droppable-message-inspector"></a>Пример: инспектор сообщений, допускающий удаление.  
 Включенный в пример образец реализации `ChannelMessageInspector` удаляет сообщения.  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 Его можно открыть из конфигурации следующим образом:  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"   
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 Клиент и сервер используют заново созданный раздел конфигурации, чтобы добавить пользовательские фабрики в самый нижний уровень принадлежащих им стеков канала времени выполнения (расположенные над транспортным уровнем).  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 Клиент использует библиотеку `MessageInterceptor`, чтобы добавить пользовательский заголовок даже в нумерованные сообщения. С другой стороны, служба использует библиотеку `MessageInterceptor`, чтобы удалять любые сообщения, которые не содержат этот специальный заголовок.  
  
 Клиент должен предоставить результат своей работы после запуска службы и последующего запуска клиента.  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 Клиент отправляет отчет службе о 10 различных значениях скорости ветра, но только половина этих значений помечена специальным заголовком.  
  
 Служба должна предоставить следующие результаты:  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Установите ASP.NET 4,0 с помощью следующей команды.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5. Первым запустите файл Service.exe, затем Client.exe и наблюдайте результат в обоих окнах консоли.  
