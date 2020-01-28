---
title: 'Шаблоны разработки: публикация-подписка на основе списка'
ms.date: 03/30/2017
ms.assetid: f4257abc-12df-4736-a03b-0731becf0fd4
ms.openlocfilehash: 3a62b09a29ec0b7e241bf2fdc09df6eaba5420c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728831"
---
# <a name="design-patterns-list-based-publish-subscribe"></a>Шаблоны разработки: публикация-подписка на основе списка
В этом примере показан шаблон публикации-подписки на основе списка, реализованный как программа Windows Communication Foundation (WCF).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Шаблон проектирования публикации и подписки на основе списка описан в статье шаблоны Microsoft patterns & методики публикации, [Шаблоны интеграции](https://docs.microsoft.com/previous-versions/msp-n-p/ff647309(v=pandp.10)). Шаблон публикации-подписки передает информацию коллекции получателей, подписавшихся на информационный раздел. Шаблон публикации-подписки на основе списка поддерживает список подписчиков. Если имеется информация для обмена, копия отправляется каждому подписчику в списке. В этом образце демонстрируется динамический шаблон публикации-подписки на основе списка, в котором клиенты могут подписываться или отказываться от подписки так часто, как требуется.  
  
 Образец шаблона публикации-подписки на основе списка состоит из клиента, службы и программы источника данных. Одновременно могут выполняться несколько клиентов и несколько программ источника данных. Клиенты подписываются на службу, получают уведомления и отказываются от подписки. Программы источника данных отправляют информацию службе для обмена со всеми текущими подписчиками.  
  
 В этом образце клиент и источник данных являются консольными программами (файлы EXE), а служба - библиотекой (.dll), размещенной в IIS. Деятельность клиента и источника данных отображается на рабочем столе.  
  
 Служба использует дуплексную связь. Контракт службы `ISampleContract` объединен с контрактом обратного вызова `ISampleClientCallback`. Служба реализует операции службы подписки и отказа от подписки, которые используются клиентами для присоединения к списку подписчиков и выхода из него. Служба также реализует операцию службы `PublishPriceChange`, которую программа источника данных вызывает для предоставления службе новой информации. Программа клиента реализует операцию службы `PriceChange`, вызываемую службой, чтобы уведомить всех подписчиков об изменении цены.  
  
```csharp  
// Create a service contract and define the service operations.  
// NOTE: The service operations must be declared explicitly.  
[ServiceContract(SessionMode=SessionMode.Required,  
      CallbackContract=typeof(ISampleClientContract))]  
public interface ISampleContract  
{  
    [OperationContract(IsOneWay = false, IsInitiating=true)]  
    void Subscribe();  
    [OperationContract(IsOneWay = false, IsTerminating=true)]  
    void Unsubscribe();  
    [OperationContract(IsOneWay = true)]  
    void PublishPriceChange(string item, double price,   
                                     double change);  
}  
  
public interface ISampleClientContract  
{  
    [OperationContract(IsOneWay = true)]  
    void PriceChange(string item, double price, double change);  
}  
```  
  
 Служба использует событие среды .NET Framework в качестве механизма информирования всех подписчиков о поступлении новых сведений. Когда клиент присоединяется к службе, вызывая метод Subscribe, он предоставляет обработчик событий. Когда клиент покидает службу, он отказывается от подписки на событие для своего обработчика событий. Если источник данных вызывает службу, чтобы сообщить об изменении цены, служба создает событие. При этом вызывается каждый экземпляр службы (по одному для каждого подписавшегося клиента), и в результате выполняются их обработчики событий. Каждый обработчик событий передает информацию своему клиенту с помощью функции обратного вызова.  
  
```csharp
public class PriceChangeEventArgs : EventArgs  
    {  
        public string Item;  
        public double Price;  
        public double Change;  
    }  
  
    // The Service implementation implements your service contract.  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    public class SampleService : ISampleContract  
    {  
        public static event PriceChangeEventHandler PriceChangeEvent;  
        public delegate void PriceChangeEventHandler(object sender, PriceChangeEventArgs e);  
  
        ISampleClientContract callback = null;  
  
        PriceChangeEventHandler priceChangeHandler = null;  
  
        //Clients call this service operation to subscribe.  
        //A price change event handler is registered for this client instance.  
  
        public void Subscribe()  
        {  
            callback = OperationContext.Current.GetCallbackChannel<ISampleClientContract>();  
            priceChangeHandler = new PriceChangeEventHandler(PriceChangeHandler);  
            PriceChangeEvent += priceChangeHandler;  
        }  
  
        //Clients call this service operation to unsubscribe.  
        //The previous price change event handler is unregistered.  
  
        public void Unsubscribe()  
        {  
            PriceChangeEvent -= priceChangeHandler;  
        }  
  
        //Information source clients call this service operation to report a price change.  
        //A price change event is raised. The price change event handlers for each subscriber will execute.  
  
        public void PublishPriceChange(string item, double price, double change)  
        {  
            PriceChangeEventArgs e = new PriceChangeEventArgs();  
            e.Item = item;  
            e.Price = price;  
            e.Change = change;  
            PriceChangeEvent(this, e);  
        }  
  
        //This event handler runs when a PriceChange event is raised.  
        //The client's PriceChange service operation is invoked to provide notification about the price change.  
  
        public void PriceChangeHandler(object sender, PriceChangeEventArgs e)  
        {  
            callback.PriceChange(e.Item, e.Price, e.Change);  
        }  
  
    }  
```  
  
 При выполнении образца необходимо запускать несколько клиентов. Клиенты подписываются на службу. Затем необходимо выполнить программу источника данных, которая отправляет информацию службе. Служба передает информацию всем подписчикам. На консоли каждого клиента можно видеть выполняемые действия, подтверждающие, что информация была получена. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>Запуск образца на том же компьютере  
  
1. Проверьте, что доступ к службе можно получить с помощью браузера, введя следующий адрес: `http://localhost/servicemodelsamples/service.svc`. Должна отобразиться страница подтверждения.  
  
2. Запустите файл Client. exe из \client\bin\\\в папке для конкретного языка. Действия клиента отображаются в окне консоли клиента. Запустите несколько клиентов.  
  
3. Запустите файл DataSource. exe из \датасаурце\бин\\в папке для конкретного языка. Действия источника данных отображаются в окне консоли. После того, как источник данных отправляет информацию службе, она должна быть передана каждому клиенту.  
  
4. Если клиент, источник данных и служебные программы не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-machines"></a>Выполнение примера на нескольких компьютерах  
  
1. Настройка компьютера службы.  
  
    1. На компьютере службы создайте виртуальный каталог с именем ServiceModelSamples. Пакетный файл Setupvroot. bat из [процедуры однократной настройки для примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) можно использовать для создания каталога диска и виртуального каталога.  
  
    2. Скопируйте файлы программы службы из каталога %SystemDrive%\Inetpub\wwwroot\servicemodelsamples в виртуальный каталог ServiceModelSamples на компьютере службы. Не забудьте включить файлы в каталог \bin.  
  
    3. Убедитесь, что доступ к службе с клиентского компьютера можно получить из браузера.  
  
2. Настройка клиентских компьютеров.  
  
    1. Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в языковой папке.  
  
    2. В каждом файле конфигурации клиента измените значение адреса определения конечной точки, чтобы оно соответствовало новому адресу службы. Замените любые ссылки на "localhost" в адресе полным именем домена.  
  
3. Настройка компьютера источника данных.  
  
    1. Скопируйте на компьютер источника данных файлы программы источника данных из папки \datasource\bin\ в языковой папке.  
  
    2. В файле конфигурации источника данных измените значение адреса определения конечной точки, чтобы оно соответствовало новому адресу службы. Замените любые ссылки на "localhost" в адресе полным именем домена.  
  
4. На клиентских компьютерах запустите из командной строки программу Client.exe.  
  
5. На компьютере источника данных запустите из окна командной строки программу Datasource.exe.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DesignPatterns/ListBasedPublishSubscribe`  
