---
title: "Практическое руководство. Настройка базового клиента Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "клиенты WCF [WCF], настройка"
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# Практическое руководство. Настройка базового клиента Windows Communication Foundation
Это первый из пяти шагов, необходимых для создания базового приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 В этом разделе рассматривается файл конфигурации клиента, сформированный с использованием функции добавления ссылки на службу в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] или с использованием [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  Настройка клиента состоит из задания конечной точки, которую клиент использует для получения доступа к службе.  Конечная точка имеет адрес, привязку и контракт, и при настройке клиента необходимо задать все эти элементы.  
  
### Настройка клиента Windows Communication Foundation  
  
1.  Откройте сформированный файл конфигурации \(App.config\) из проекта GettingStartedClient.  В следующем примере приведено представление созданного файла конфигурации.  В разделе [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)[\<endpoint\> найдите элемент](http://msdn.microsoft.com/ru-ru/13aa23b7-2f08-4add-8dbf-a99f8127c017).  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration><?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     В этом примере продемонстрирована настройка конечной точки, которую клиент использует для получения доступа к службе, расположенной по следующему адресу: http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService  
  
     В элементе конечной точки указано, что контракт службы `ServiceReference1.ICalculator` используется для взаимодействия между клиентом и службой WCF.  Канал WCF настроен с привязкой <xref:System.ServiceModel.WsHttpBinding>, предоставленной системой.  Этот контракт был сформирован с использованием функции добавления ссылки на службу в Visual Studio.  В сущности, это является копией контракта, определенного в проекте GettingStartedLib.  Привязка <xref:System.ServiceModel.WsHttpBinding> задает HTTP в качестве транспорта, уровень безопасности и другие данные конфигурации.  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] использовании созданного клиента с этой конфигурацией см. раздел [Практическое руководство. Использование клиента](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## См. также  
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Как создать клиент](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)