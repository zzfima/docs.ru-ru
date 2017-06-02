---
title: "Практическое руководство. Настройка параметров службы COM+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "COM+ [WCF], настройка параметров служб"
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Практическое руководство. Настройка параметров службы COM+
Если интерфейс приложения добавляется или удаляется с использованием средства конфигурации служб COM\+, конфигурация веб\-службы обновляется в файле конфигурации приложения.  В режиме размещение в COM\+ файл Application.config помещается в корневую папку приложения \(по умолчанию %PROGRAMFILES%\\ComPlus Applications\\{appid}\).  В обоих режимах размещения на веб\-сервере файл Web.config помещается в заданный виртуальный корневой каталог.  
  
> [!NOTE]
>  Для защиты от подделки сообщений, обмен которыми выполняется между клиентом и сервером, необходимо использовать подписывание сообщения.  Кроме того, для защиты от раскрытия информации, содержащейся в сообщениях, обмен которыми выполняется между клиентом и сервером, следует использовать шифрование на уровне сообщения или транспорта.  Как и в случае служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] необходимо использовать функцию регулирования, чтобы ограничить количество одновременных вызовов, подключений, экземпляров и отложенных операций.  Это помогает предотвратить чрезмерное потребление ресурсов.  Поведение регулирования задается параметрами файла конфигурации службы.  
  
## Пример  
 Рассмотрим компонент, реализующий следующий интерфейс.  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
  
```  
  
 Если компонент предоставляется как веб\-служба, соответствующий предоставляемый контракт службы, которому должны соответствовать клиенты, выглядит следующим образом.  
  
```  
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
  
```  
  
> [!NOTE]
>  Идентификатор интерфейса формирует часть исходного пространства имен для контракта.  
  
 Клиентские приложения, использующие эту службу, должны соответствовать этому контракту, а также использовать привязку, совместимую с привязкой, заданной в конфигурации приложения.  
  
 В следующем примере кода показан файл конфигурации по умолчанию.  Являясь веб\-службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], он соответствует стандартной схеме конфигурации модели службы, и его можно изменить так же, как другие файлы конфигурации служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Типичные изменения включают следующее.  
  
-   Изменение адреса конечной точки с формы ApplicationName\/ComponentName\/InterfaceName по умолчанию на более удобную форму.  
  
-   Изменение пространства имен службы с формы "http:\/\/tempuri.org\/InterfaceID" по умолчанию на более подходящую форму.  
  
-   Изменение настройки конечной точки, чтобы она использовала другую привязку транспорта.  
  
     В случае размещения в COM\+ по умолчанию используется транспорт именованных каналов, но вместо него можно использовать транспорт вне компьютера, такой как TCP.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
  
```  
  
## См. также  
 [Интеграция с приложениями COM\+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)