---
title: "Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation
Ниже описано, как перенести веб\-службу ASP.NET на платформу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] .  
  
## Процедура  
  
#### Перенос кода службы ASP.NET в WCF  
  
1.  Проверьте наличие полного набора тестов для службы.  
  
2.  Создайте код WSDL для службы и сохраните копию в той же папке, что и файл ASMX службы.  
  
3.  Обновите веб\-службу ASP.NET для использования .NET 2.0.  Сначала разверните .NET Framework 2.0 в приложение в службах IIS, а затем с помощью Visual Studio 2005 автоматически преобразуйте код, как описано в документе [Пошаговое руководство по преобразованию веб\-проектов из Visual Studio .NET 2002\/2003 в Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).  Выполните набор тестов.  
  
4.  Задайте явные значения параметров `Namespace` и `Name` атрибутов <xref:System.Web.Services.WebService>, если они еще не заданы.  Выполните те же действия для параметра `MessageName` атрибута <xref:System.Web.Services.WebMethodAttribute>.  Если явные значения еще не заданы в HTTP\-заголовках SOAPAction, с помощью которых запросы перенаправляются в методы, явным образом укажите значение по умолчанию параметра `Action` с атрибутом <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
5.  Протестируйте изменения.  
  
6.  Переместите важный код в телах методов класса в отдельный класс, который может использоваться исходным классом.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
    }  
  
    internal class ActualAdder  
    {  
         internal double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
7.  Протестируйте изменения.  
  
8.  Добавьте ссылки на сборки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] System.ServiceModel и System.Runtime.Serialization в проект веб\-службы ASP.NET.  
  
9. Запустите средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), чтобы создать класс клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] из кода WSDL.  Добавьте модуль созданного класса в решение.  
  
10. Модуль класса, созданный на предыдущем шаге, содержит определение интерфейса.  
  
    ```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface AdderSoap  
    {  
         [System.ServiceModel.OperationContractAttribute(  
          Action="http://tempuri.org/Add",   
          ReplyAction="http://tempuri.org/Add")]  
         AddResponse Add(AddRequest request);  
    }  
    ```  
  
     Измените определение класса веб\-службы ASP.NET, чтобы класс был определен как реализация этого интерфейса, как показано в следующем примере кода.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder: AdderSoap  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
            return new AddResponse(  
            new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
11. Скомпилируйте проект.  Могут обнаружиться некоторые ошибки, связанные с кодом, созданным на шаге девять, когда были скопированы некоторые определения.  Исправьте эти ошибки. Обычно для этого достаточно удалить ранее заданные определения типов.  Протестируйте изменения.  
  
12. Удалите атрибуты, относящиеся к ASP.NET, например <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> и <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.  
  
    ```  
    public class Adder: AdderSoap  
    {  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
              return new AddResponse(  
             new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
13. Настройте класс, которые теперь является типом службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], чтобы он требовал режима совместимости [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET, если веб\-служба ASP.NET использовала какие\-либо компоненты из следующего списка:  
  
    -   класс <xref:System.Web.HttpContext>;  
  
    -   профили ASP.NET;  
  
    -   списки управления доступом к файлам ASMX;  
  
    -   параметры проверки подлинности IIS;  
  
    -   параметры олицетворения ASP.NET;  
  
    -   глобализация ASP.NET.  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. Переименуйте исходный файл ASMX в ASMX.OLD.  
  
15. Создайте файл службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], присвойте ему расширение ASMX и сохраните его в корневой папке приложения в IIS.  
  
    ```  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. Добавьте конфигурацию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы в файл Web.config.  Настройте службу, чтобы она использовала элемент [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), файл службы с расширением ASMX, созданный на предыдущих шагах, и не создавала для себя код WSDL, используя вместо этого код WSDL, полученный на шаге два.  Кроме того, при необходимости настройте режим совместимости ASP.NET.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.web>  
      <compilation>  
      <buildProviders>  
       <remove extension=".asmx" />  
       <add extension=".asmx"   
        type=  
        "System.ServiceModel.Activation.ServiceBuildProvider,  
        T:System.ServiceModel, Version=2.0.0.0,   
       Culture=neutral,   
       PublicKeyToken=b77a5c561934e089" />  
      </buildProviders>  
      </compilation>  
     </system.web>  
     <system.serviceModel>  
      <services>  
      <service name="MyOrganization.Adder "  
        behaviorConfiguration="AdderBehavior">  
       <endpoint   
        address="”  
        binding="basicHttpBinding"  
        contract="AdderSoap "/>  
       </service>  
      </services>  
      <behaviors>  
      <behavior name="AdderBehavior">  
       <metadataPublishing   
        enableMetadataExchange="true"   
        enableGetWsdl="true"   
        enableHelpPage="true"   
        metadataLocation=  
        "http://MyHost.com/AdderService/Service.WSDL"/>  
      </behavior>  
      </behaviors>  
      <serviceHostingEnvironment   
       aspNetCompatibilityEnabled ="true"/>  
     </system.serviceModel>  
    </configuration>  
  
    ```  
  
17. Сохраните конфигурацию.  
  
18. Скомпилируйте проект.  
  
19. Выполните набор тестов, чтобы убедиться, что все изменения работают.  
  
## См. также  
 [Практическое руководство. Миграция кода клиента веб\-службы ASP.NET на платформу Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)