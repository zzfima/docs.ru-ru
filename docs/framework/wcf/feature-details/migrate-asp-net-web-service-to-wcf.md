---
title: "Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 94d6cc499caddc8b3cbbf8ba7845e4de5441165c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="091a0-102">Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="091a0-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="091a0-103">Ниже описано, как перенести веб-службу ASP.NET на платформу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="091a0-103">The following procedure describes how to migrate an ASP.NET Web Service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="091a0-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="091a0-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="091a0-105">Перенос кода службы ASP.NET в WCF</span><span class="sxs-lookup"><span data-stu-id="091a0-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="091a0-106">Проверьте наличие полного набора тестов для службы.</span><span class="sxs-lookup"><span data-stu-id="091a0-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="091a0-107">Создайте код WSDL для службы и сохраните копию в той же папке, что и файл ASMX службы.</span><span class="sxs-lookup"><span data-stu-id="091a0-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="091a0-108">Обновите веб-службу ASP.NET для использования .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="091a0-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="091a0-109">Сначала разверните .NET Framework 2.0 приложение в службах IIS, а затем использовать Visual Studio 2005 для автоматизации процесса преобразования кода, как описано в [Пошаговое руководство по преобразованию веб-проектов из Visual Studio .NET 2002/2003 в Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span><span class="sxs-lookup"><span data-stu-id="091a0-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="091a0-110">Выполните набор тестов.</span><span class="sxs-lookup"><span data-stu-id="091a0-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="091a0-111">Задайте явные значения параметров `Namespace` и `Name` атрибутов <xref:System.Web.Services.WebService>, если они еще не заданы.</span><span class="sxs-lookup"><span data-stu-id="091a0-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="091a0-112">Выполните те же действия для параметра `MessageName` атрибута <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="091a0-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="091a0-113">Если явные значения еще не заданы в HTTP-заголовках SOAPAction, с помощью которых запросы перенаправляются в методы, явным образом укажите значение по умолчанию параметра `Action` с атрибутом <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="091a0-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
5.  <span data-ttu-id="091a0-114">Протестируйте изменения.</span><span class="sxs-lookup"><span data-stu-id="091a0-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="091a0-115">Переместите важный код в телах методов класса в отдельный класс, который может использоваться исходным классом.</span><span class="sxs-lookup"><span data-stu-id="091a0-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
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
  
7.  <span data-ttu-id="091a0-116">Протестируйте изменения.</span><span class="sxs-lookup"><span data-stu-id="091a0-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="091a0-117">Добавьте ссылки на сборки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] System.ServiceModel и System.Runtime.Serialization в проект веб-службы ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="091a0-117">Add references to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="091a0-118">Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] класс клиента из WSDL.</span><span class="sxs-lookup"><span data-stu-id="091a0-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class from the WSDL.</span></span> <span data-ttu-id="091a0-119">Добавьте модуль созданного класса в решение.</span><span class="sxs-lookup"><span data-stu-id="091a0-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="091a0-120">Модуль класса, созданный на предыдущем шаге, содержит определение интерфейса.</span><span class="sxs-lookup"><span data-stu-id="091a0-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
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
  
     <span data-ttu-id="091a0-121">Измените определение класса веб-службы ASP.NET, чтобы класс был определен как реализация этого интерфейса, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="091a0-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
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
  
11. <span data-ttu-id="091a0-122">Скомпилируйте проект.</span><span class="sxs-lookup"><span data-stu-id="091a0-122">Compile the project.</span></span> <span data-ttu-id="091a0-123">Могут обнаружиться некоторые ошибки, связанные с кодом, созданным на шаге девять, когда были скопированы некоторые определения.</span><span class="sxs-lookup"><span data-stu-id="091a0-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="091a0-124">Исправьте эти ошибки. Обычно для этого достаточно удалить ранее заданные определения типов.</span><span class="sxs-lookup"><span data-stu-id="091a0-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="091a0-125">Протестируйте изменения.</span><span class="sxs-lookup"><span data-stu-id="091a0-125">Test the change.</span></span>  
  
12. <span data-ttu-id="091a0-126">Удалите атрибуты, относящиеся к ASP.NET, например <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> и <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="091a0-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
13. <span data-ttu-id="091a0-127">Настройте класс, которые теперь является типом службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], чтобы он требовал режима совместимости [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET, если веб-служба ASP.NET использовала какие-либо компоненты из следующего списка:</span><span class="sxs-lookup"><span data-stu-id="091a0-127">Configure the class, which is now a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service type, to require [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="091a0-128">класс <xref:System.Web.HttpContext>;</span><span class="sxs-lookup"><span data-stu-id="091a0-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="091a0-129">профили ASP.NET;</span><span class="sxs-lookup"><span data-stu-id="091a0-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="091a0-130">списки управления доступом к файлам ASMX;</span><span class="sxs-lookup"><span data-stu-id="091a0-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="091a0-131">параметры проверки подлинности IIS;</span><span class="sxs-lookup"><span data-stu-id="091a0-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="091a0-132">параметры олицетворения ASP.NET;</span><span class="sxs-lookup"><span data-stu-id="091a0-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="091a0-133">глобализация ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="091a0-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="091a0-134">Переименуйте исходный файл ASMX в ASMX.OLD.</span><span class="sxs-lookup"><span data-stu-id="091a0-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="091a0-135">Создайте файл службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], присвойте ему расширение ASMX и сохраните его в корневой папке приложения в IIS.</span><span class="sxs-lookup"><span data-stu-id="091a0-135">Create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="091a0-136">Добавьте конфигурацию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы в файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="091a0-136">Add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration for the service to its Web.config file.</span></span> <span data-ttu-id="091a0-137">Настройте службу на использование [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), для использования службы файла с расширением .asmx, созданные на предыдущем шаге и не формирует WSDL-код для себя, но для использования WSDL из шага 2.</span><span class="sxs-lookup"><span data-stu-id="091a0-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="091a0-138">Кроме того, при необходимости настройте режим совместимости ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="091a0-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
    ```xml  
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
        address=""  
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
  
17. <span data-ttu-id="091a0-139">Сохраните конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="091a0-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="091a0-140">Скомпилируйте проект.</span><span class="sxs-lookup"><span data-stu-id="091a0-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="091a0-141">Выполните набор тестов, чтобы убедиться, что все изменения работают.</span><span class="sxs-lookup"><span data-stu-id="091a0-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091a0-142">См. также</span><span class="sxs-lookup"><span data-stu-id="091a0-142">See Also</span></span>  
 [<span data-ttu-id="091a0-143">Как: Миграция кода клиента службы ASP.NET на платформу Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="091a0-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
