---
title: Доступ к службам WCF из клиентского приложения Магазина Windows
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: b4b91c103aa91e3b2c9e811c642a8347c7db1a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185485"
---
# <a name="accessing-wcf-services-with-a-windows-store-client-app"></a>Доступ к службам WCF из клиентского приложения Магазина Windows
В Windows 8 появился новый тип приложения - приложения Магазина Windows. Эти приложения предназначены для работы с сенсорным экраном. .NET Framework 4.5 позволяет приложениям Магазина Windows вызывать службы WCF.  
  
## <a name="wcf-support-in-windows-store-applications"></a>Поддержка WCF в приложениях Магазина Windows.  
 Подмножество функций WCF доступно из приложения Магазина Windows. Дополнительную информацию см. в следующих разделах.  
  
> [!IMPORTANT]
> Используйте API-синдикации WinRT вместо методов, доступных через службу WCF. Дополнительные сведения см. в разделе [API синдикации WinRT](xref:Windows.Web.Syndication)  
  
> [!WARNING]
> Использование диалогового окна «Добавление ссылки на службу» для добавления ссылки на веб-службу в компонент среды выполнения Windows не поддерживается.  
  
### <a name="supported-bindings"></a>Поддерживаемые привязки  
 Поддерживаются следующие привязки WCF в приложениях Магазина Windows:  
  
1. <xref:System.ServiceModel.BasicHttpBinding>  
  
2. <xref:System.ServiceModel.NetTcpBinding>  
  
3. <xref:System.ServiceModel.NetHttpBinding>  
  
4. <xref:System.ServiceModel.Channels.CustomBinding>
  
 Поддерживаются следующие элементы привязки в приложениях Магазина Windows  
  
1. <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2. <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3. <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4. <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5. <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6. <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7. <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8. <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Поддерживается текстовое и двоичное кодирование. Поддерживаются все режимы передачи WCF. Дополнительные сведения см. в разделе [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).  
  
### <a name="add-service-reference"></a>Добавление ссылки на службу  
 Для вызова службы WCF из приложения Магазина Windows пользуйтесь функцией «Добавить ссылку на службу» среды Visual Studio 2012. Можно заметить небольшие изменения в работе функции «Добавить ссылку на службу» при работе с приложением Магазина Windows. Во-первых, не создается файл конфигурации. Приложения Магазина Windows не используют файлы конфигурации, поэтому их необходимо настраивать в коде. Код конфигурации можно найти в файле References.cs, который создается функцией «Добавить ссылку на службу». Чтобы увидеть этот файл, не забудьте выбрать "Показать все файлы" в проводнике решения. Файл будет расположен под пунктом «Ссылки на службу», а затем в узлах Reference.svcmap в рамках проекта. Все операции, созданные для служб WCF внутри приложения Магазина Windows, будут асинхронными, использующими асинхронную технологию на основе событий. Для получения дополнительной [Async Tasks - Simplify Asynchronous Programming with Tasks](https://docs.microsoft.com/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks)информации см.  
  
 Поскольку конфигурация создается в коде, любые изменения, внесенные в файл Reference.cs, будут перезаписываться при каждом обновлении ссылки на службу. Чтобы исправить эту ситуацию, код конфигурации создается внутри разделяемого метода, который вы можно реализовать в клиентском прокси-классе. Разделяемый метод определяется следующим образом:  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 Затем можно реализовать этот разделяемый метод и изменить привязку или конечную точку в клиентском прокси-классе следующим образом:  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a>Сериализация  
 Поддерживаются следующие сериализаторы WCF в приложениях Магазина Windows:  
  
1. DataContractSerializer  
  
2. DataContractJsonSerializer  
  
3. XmlSerializer  
  
> [!WARNING]
> XmlDictionaryWriter.Write (DateTime) теперь записывает объект DateTime в виде строки.  
  
### <a name="security"></a>Безопасность  

Следующие режимы безопасности поддерживаются в приложениях Магазина Windows:
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
Следующие типы учетных данных клиентов поддерживаются в приложениях Магазина Windows:
  
1. None  
  
2. Basic  
  
3. Дайджест  
  
4. Согласование  
  
5. NTLM  
  
6. Windows  
  
7. Имя пользователя (безопасность сообщений)  
  
8. Windows (безопасность транспорта)  
  
 Чтобы приложения Магазина Windows могли получать и передавать учетные данные Windows по умолчанию, необходимо включить эту возможность в файле Package.appmanifest. Откройте этот файл и выберите вкладку «Возможности для Windows» и выберите «Учетные данные Windows по умолчанию». Это позволит приложению подключаться к ресурсам интрасети, для доступа к которым требуются учетные данные домена.  
  
> [!IMPORTANT]
> Для того, чтобы приложения Магазина Windows могли совершать перекрестные вызовы, необходимо включить еще одну возможность под названием "Домашняя/Рабочая сеть". Эта настройка также находится в файле Package.appmanifest под вкладкой «Возможности. Выберите чекбокс Home/Work Networking». Приложение получит входящий и исходящий доступ к доверенным сетям пользователя - домашней и рабочей. Важные входящие порты всегда заблокированы. Для доступа к службам в Интернете необходимо также включить возможность «Интернет (клиент)».  
  
### <a name="misc"></a>Разное  
 Поддерживается использование следующих классов для приложений Магазина Windows:  
  
1. <xref:System.ServiceModel.ChannelFactory>  
  
2. <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3. <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a>Определение контрактов службы  
 Рекомендуется определять только асинхронные операции службы с помощью асинхронной модели на основе событий. Это гарантирует, что приложения Магазина Windows сохранят высокую скорость отклика при вызове операции службы.  
  
> [!WARNING]
> Хотя исключение не возникнет, если указать синхронную операцию, настоятельно рекомендуется определять только асинхронные операции.  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a>Вызов служб WCF из приложений Магазина Windows  
 Как уже говорилось, вся настройка должна быть сделана в коде метода GetBindingForEndpoint в сформированном прокси-классе. Вызов операции службы выполняется точно так же, как и вызов любого асинхронного метода, как показано в следующем фрагменте кода.  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 Обратите внимание на использование ключевого слова async при асинхронном вызове, а также ключевого слова await при вызове асинхронного метода.  
  
## <a name="see-also"></a>См. также раздел

- [WCF в блоге о приложениях для Магазина Windows](https://docs.microsoft.com/archive/blogs/piyushjo/wcf-in-windows-8-metro-styled-apps-absolutely-supported)
- [Клиенты магазина Windows WCF и безопасность](https://docs.microsoft.com/archive/blogs/piyushjo/calling-a-wcf-service-from-a-metro-application-adding-security)
- [Приложения для магазина Windows и межкомпьютерные вызовы](https://docs.microsoft.com/archive/blogs/piyushjo/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario)
- [Вызов службы WCF, развернутой в Azure из приложения для магазина Windows](https://docs.microsoft.com/archive/blogs/piyushjo/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario)
- [Программирование безопасности WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [Привязки](../../../../docs/framework/wcf/bindings.md)
