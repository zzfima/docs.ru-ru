---
title: Настройка служб с использованием файлов конфигурации
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62a8774ab2843d0b1f0a19ad04fc0a76abb7cac5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-services-using-configuration-files"></a><span data-ttu-id="2e65d-102">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="2e65d-102">Configuring Services Using Configuration Files</span></span>
<span data-ttu-id="2e65d-103">Настройка службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] с помощью файла конфигурации обеспечивает гибкость предоставления данных по конечной точке и поведению службы непосредственно в точке развертывания, а не во время разработки.</span><span class="sxs-lookup"><span data-stu-id="2e65d-103">Configuring a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service with a configuration file gives you the flexibility of providing endpoint and service behavior data at the point of deployment instead of at design time.</span></span> <span data-ttu-id="2e65d-104">В этой теме представлено описание основных доступных методов.</span><span class="sxs-lookup"><span data-stu-id="2e65d-104">This topic outlines the primary techniques available.</span></span>  
  
 <span data-ttu-id="2e65d-105">Службу [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] можно настроить с помощью технологии конфигурации [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e65d-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="2e65d-106">Чаще всего элементы XML добавляются в файл Web.config для узла служб IIS, на котором размещена служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e65d-106">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="2e65d-107">Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер.</span><span class="sxs-lookup"><span data-stu-id="2e65d-107">The elements allow you to change details such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span> <span data-ttu-id="2e65d-108">Кроме того, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] включает в себя несколько предоставляемых системой элементов, которые позволяют быстро выбрать для службы самые основные функции.</span><span class="sxs-lookup"><span data-stu-id="2e65d-108">In addition, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] includes several system-provided elements that allow you to quickly select the most basic features for a service.</span></span> <span data-ttu-id="2e65d-109">Начиная с версии [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], в [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] входит новая модель конфигурации по умолчанию, которая обладает упрощенными требованиями к настройке [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e65d-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] comes with a new default configuration model that simplifies [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration requirements.</span></span> <span data-ttu-id="2e65d-110">Если для службы не указана конфигурация [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , то среда выполнения автоматически выполняет настройку службы, указывая некоторые стандартные конечные точки, привязку и поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e65d-110">If you do not provide any [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration for a particular service, the runtime automatically configures your service with some standard endpoints and default binding/behavior.</span></span> <span data-ttu-id="2e65d-111">На практике запись конфигурации является основной частью процесса программирования приложений [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e65d-111">In practice, writing configuration is a major part of programming [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="2e65d-112">Дополнительные сведения см. в разделе [Настройка привязок для служб](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e65d-112">For more information, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span> <span data-ttu-id="2e65d-113">Список наиболее часто используемые элементы, см. в разделе [привязка, предоставляемая системой](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="2e65d-113">For a list of of the most commonly used elements, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="2e65d-114">Дополнительные сведения о конечных точек по умолчанию, привязок и поведений см. в разделе [упрощенной конфигурации](../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e65d-114">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e65d-115">При развертывании сценариев параллельного выполнения, в которых развернуты две различные версии службы, необходимо указывать частичные имена сборок, на которые ссылаются файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e65d-115">When deploying side by side scenarios where two different versions of a service are deployed, it is necessary to specify partial names of assemblies referenced in configuration files.</span></span> <span data-ttu-id="2e65d-116">Это связано с тем, что файл конфигурации совместно используется всеми версиями службы, которые могут выполняться под управлением различных версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e65d-116">This is because the configuration file is shared across all versions of a service and they could be running under different versions of the .NET Framework.</span></span>  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a><span data-ttu-id="2e65d-117">System.Configuration: Web.config и App.config</span><span class="sxs-lookup"><span data-stu-id="2e65d-117">System.Configuration: Web.config and App.config</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="2e65d-118"> использует систему конфигурации System.Configuration [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e65d-118"> uses the System.Configuration configuration system of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="2e65d-119">При настройке службы в Visual Studio, используйте файл Web.config или файла App.config для указания параметров.</span><span class="sxs-lookup"><span data-stu-id="2e65d-119">When configuring a service in Visual Studio, use either a Web.config file or an App.config file to specify the settings.</span></span> <span data-ttu-id="2e65d-120">Выбор имени файла конфигурации определяется выбранной для службы средой размещения.</span><span class="sxs-lookup"><span data-stu-id="2e65d-120">The choice of the configuration file name is determined by the hosting environment you choose for the service.</span></span> <span data-ttu-id="2e65d-121">Если служба размещается с помощью IIS, используйте файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="2e65d-121">If you are using IIS to host your service, use a Web.config file.</span></span> <span data-ttu-id="2e65d-122">Если служба размещается с помощью другой среды размещения, используйте файл App.config.</span><span class="sxs-lookup"><span data-stu-id="2e65d-122">If you are using any other hosting environment, use an App.config file.</span></span>  
  
 <span data-ttu-id="2e65d-123">В Visual Studio файл с именем App.config используется для создания окончательного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e65d-123">In Visual Studio, the file named App.config is used to create the final configuration file.</span></span> <span data-ttu-id="2e65d-124">Окончательное имя, которое фактически используется для конфигурации, зависит от имени сборки.</span><span class="sxs-lookup"><span data-stu-id="2e65d-124">The final name actually used for the configuration depends on the assembly name.</span></span> <span data-ttu-id="2e65d-125">Например, сборка с именем "Cohowinery.exe" имеет имя окончательного файла конфигурации "Cohowinery.exe.config".</span><span class="sxs-lookup"><span data-stu-id="2e65d-125">For example, an assembly named "Cohowinery.exe" has a final configuration file name of "Cohowinery.exe.config".</span></span> <span data-ttu-id="2e65d-126">Однако следует изменить только файл App.config.</span><span class="sxs-lookup"><span data-stu-id="2e65d-126">However, you only need to modify the App.config file.</span></span> <span data-ttu-id="2e65d-127">Изменения, внесенные в это файл, автоматически вносятся в окончательный файл конфигурации приложения во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="2e65d-127">Changes made to that file are automatically made to the final application configuration file at compile time.</span></span>  
  
 <span data-ttu-id="2e65d-128">При использовании файла App.config система конфигурации объединяет файл App.config с содержимым файла Machine.config, когда запускается приложение и применяется конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2e65d-128">In using an App.config, file the configuration system merges the App.config file with content of the Machine.config file when the application starts and the configuration is applied.</span></span> <span data-ttu-id="2e65d-129">Этот механизм позволяет определить параметры в рамках всего компьютера в файле Machine.config.</span><span class="sxs-lookup"><span data-stu-id="2e65d-129">This mechanism allows machine-wide settings to be defined in the Machine.config file.</span></span> <span data-ttu-id="2e65d-130">Файл App.config можно использовать для переопределения параметров файла Machine.config. Также предусмотрена возможность блокировки в параметрах файла Machine.config согласно привычной работе.</span><span class="sxs-lookup"><span data-stu-id="2e65d-130">The App.config file can be used to override the settings of the Machine.config file; you can also lock in the settings in Machine.config file so that they get used.</span></span> <span data-ttu-id="2e65d-131">Если используется файл конфигурации Web.config, то система объединяет файлы Web.config во всех родительских каталогах вплоть до каталога приложения в применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e65d-131">In the Web.config case, the configuration system merges the Web.config files in all directories leading up to the application directory into the configuration that gets applied.</span></span> <span data-ttu-id="2e65d-132">Дополнительные сведения о конфигурации и приоритетах параметров см. в подразделах <xref:System.Configuration> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2e65d-132">For more information about configuration and the setting priorities, see topics in the <xref:System.Configuration> namespace.</span></span>  
  
## <a name="major-sections-of-the-configuration-file"></a><span data-ttu-id="2e65d-133">Основные разделы файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="2e65d-133">Major Sections of the Configuration File</span></span>  
 <span data-ttu-id="2e65d-134">Основные разделы файла конфигурации включают в себя следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="2e65d-134">The main sections in the configuration file include the following elements.</span></span>  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!—- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->   
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="2e65d-135">Разделы привязок и поведения являются необязательными и указываются только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2e65d-135">The bindings and behaviors sections are optional and are only included if required.</span></span>  
  
### <a name="the-services-element"></a><span data-ttu-id="2e65d-136">\<Службы > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-136">The \<services> Element</span></span>  
 <span data-ttu-id="2e65d-137">Элемент `services` содержит спецификации для всех служб, которые размещает приложение.</span><span class="sxs-lookup"><span data-stu-id="2e65d-137">The `services` element contains the specifications for all services the application hosts.</span></span> <span data-ttu-id="2e65d-138">Начиная с упрощенной модели настройки в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], этот раздел задавать необязательно.</span><span class="sxs-lookup"><span data-stu-id="2e65d-138">Starting with the simplified configuration model in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], this section is optional.</span></span>  
  
 [<span data-ttu-id="2e65d-139">\<службы ></span><span class="sxs-lookup"><span data-stu-id="2e65d-139">\<services></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a><span data-ttu-id="2e65d-140">\<Службы > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-140">The \<service> Element</span></span>  
 <span data-ttu-id="2e65d-141">Каждая служба имеет следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="2e65d-141">Each service has these attributes:</span></span>  
  
-   <span data-ttu-id="2e65d-142">`name`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-142">`name`.</span></span> <span data-ttu-id="2e65d-143">Определяет тип, обеспечивающий реализацию контракта службы.</span><span class="sxs-lookup"><span data-stu-id="2e65d-143">Specifies the type that provides an implementation of a service contract.</span></span> <span data-ttu-id="2e65d-144">Это полное имя, состоящее из пространства имен, точки и имени типа,</span><span class="sxs-lookup"><span data-stu-id="2e65d-144">This is a fully qualified name which consists of the namespace, a period, and then the type name.</span></span> <span data-ttu-id="2e65d-145">например `"MyNameSpace.myServiceType"`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-145">For example `"MyNameSpace.myServiceType"`.</span></span>  
  
-   <span data-ttu-id="2e65d-146">`behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-146">`behaviorConfiguration`.</span></span> <span data-ttu-id="2e65d-147">Задает имя одного из элементов `behavior` , найденных в `behaviors` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-147">Specifies the name of one of the `behavior` elements found in the `behaviors` element.</span></span> <span data-ttu-id="2e65d-148">Заданное поведение управляет действиями, например, разрешает ли служба олицетворение.</span><span class="sxs-lookup"><span data-stu-id="2e65d-148">The specified behavior governs actions such as whether the service allows impersonation.</span></span> <span data-ttu-id="2e65d-149">Если значением является пустое имя, или объект `behaviorConfiguration` не указан, то в службу добавляется набор поведений службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e65d-149">If its value is the empty name or no `behaviorConfiguration` is provided then the default set of service behaviors is added to the service.</span></span>  
  
-   [<span data-ttu-id="2e65d-150">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="2e65d-150">\<service></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a><span data-ttu-id="2e65d-151">\<Endpoint > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-151">The \<endpoint> Element</span></span>  
 <span data-ttu-id="2e65d-152">Для каждой конечной точки требуется адрес, привязка и контракт, представленные следующими атрибутами:</span><span class="sxs-lookup"><span data-stu-id="2e65d-152">Each endpoint requires an address, a binding, and a contract, which are represented by the following attributes:</span></span>  
  
-   <span data-ttu-id="2e65d-153">`address`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-153">`address`.</span></span> <span data-ttu-id="2e65d-154">Задает универсальный код ресурса (URI) службы, который может быть абсолютным адресом или адресом, указанным относительно базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="2e65d-154">Specifies the service's Uniform Resource Identifier (URI), which can be an absolute address or one that is given relative to the base address of the service.</span></span> <span data-ttu-id="2e65d-155">Если задана пустая строка, это означает, что конечная точка доступна по базовому адресу, который указывается при создании <xref:System.ServiceModel.ServiceHost> для службы.</span><span class="sxs-lookup"><span data-stu-id="2e65d-155">If set to an empty string, it indicates that the endpoint is available at the base address that is specified when creating the <xref:System.ServiceModel.ServiceHost> for the service.</span></span>  
  
-   <span data-ttu-id="2e65d-156">`binding`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-156">`binding`.</span></span> <span data-ttu-id="2e65d-157">Как правило, задает предоставляемую системой привязку типа <xref:System.ServiceModel.WSHttpBinding>, но также может задавать определяемую пользователем привязку.</span><span class="sxs-lookup"><span data-stu-id="2e65d-157">Typically specifies a system-provided binding like <xref:System.ServiceModel.WSHttpBinding>, but can also specify a user-defined binding.</span></span> <span data-ttu-id="2e65d-158">Заданная привязка определяет используемый тип транспорта, безопасности и кодирования, а также поддерживаются ли или включены ли надежные сеансы, транзакции или потоковая передача.</span><span class="sxs-lookup"><span data-stu-id="2e65d-158">The binding specified determines the type of transport, security and encoding used, and whether reliable sessions, transactions, or streaming is supported or enabled.</span></span>  
  
-   <span data-ttu-id="2e65d-159">`bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-159">`bindingConfiguration`.</span></span> <span data-ttu-id="2e65d-160">Если требуется изменить значения привязки по умолчанию, можно настроить соответствующий элемент `binding` в элементе `bindings` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-160">If the default values of a binding must be modified, this can be done by configuring the appropriate `binding` element in the `bindings` element.</span></span> <span data-ttu-id="2e65d-161">Этому атрибуту должно быть присвоено то же значение, что и атрибуту `name` элемента `binding` , который используется для изменения значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e65d-161">This attribute should be given the same value as the `name` attribute of the `binding` element that is used to change the defaults.</span></span> <span data-ttu-id="2e65d-162">Если имя не задано, или в привязке не задан объект `bindingConfiguration` , то в конечной точке используется привязка по умолчанию типа привязки.</span><span class="sxs-lookup"><span data-stu-id="2e65d-162">If no name is given, or no `bindingConfiguration` is specified in the binding, then the default binding of the binding type is used in the endpoint.</span></span>  
  
-   <span data-ttu-id="2e65d-163">`contract`.</span><span class="sxs-lookup"><span data-stu-id="2e65d-163">`contract`.</span></span> <span data-ttu-id="2e65d-164">Задает интерфейс, определяющий контракт.</span><span class="sxs-lookup"><span data-stu-id="2e65d-164">Specifies the interface that defines the contract.</span></span> <span data-ttu-id="2e65d-165">Это интерфейс, реализованный в типе CLR, который задан атрибутом `name` элемента `service` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-165">This is the interface implemented in the common language runtime (CLR) type specified by the `name` attribute of the `service` element.</span></span>  
  
-   [<span data-ttu-id="2e65d-166">\<Конечная точка > Справочник по элементам</span><span class="sxs-lookup"><span data-stu-id="2e65d-166">\<endpoint> element reference</span></span>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)  
  
### <a name="the-bindings-element"></a><span data-ttu-id="2e65d-167">\<Привязки > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-167">The \<bindings> Element</span></span>  
 <span data-ttu-id="2e65d-168">Элемент `bindings` содержит спецификации для всех привязок, которые могут использоваться любой конечной точкой, заданной в любой службе.</span><span class="sxs-lookup"><span data-stu-id="2e65d-168">The `bindings` element contains the specifications for all bindings that can be used by any endpoint defined in any service.</span></span>  
  
 [<span data-ttu-id="2e65d-169">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="2e65d-169">\<bindings></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a><span data-ttu-id="2e65d-170">\<Привязки > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-170">The \<binding> Element</span></span>  
 <span data-ttu-id="2e65d-171">Элемент `binding` , содержащиеся в элементе `bindings` , могут являться одной из предоставленных системой привязок (см. раздел [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) или пользовательской привязкой (см. раздел [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="2e65d-171">The `binding` elements contained in the `bindings` element can be either one of the system-provided bindings (see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) or a custom binding (see [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="2e65d-172">Элемент `binding` имеет атрибут `name` , сопоставляющий привязку с конечной точкой, заданной в атрибуте `bindingConfiguration` элемента `endpoint` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-172">The `binding` element has a `name` attribute that correlates the binding with the endpoint specified in the `bindingConfiguration` attribute of the `endpoint` element.</span></span> <span data-ttu-id="2e65d-173">Если имя не указано, то привязка будет соответствовать значению по умолчанию для этого типа привязки.</span><span class="sxs-lookup"><span data-stu-id="2e65d-173">If no name is specified then that binding corresponds to the default of that binding type.</span></span>  
  
 <span data-ttu-id="2e65d-174">Дополнительные сведения о настройке служб и клиентов см. в разделе [Настройка приложений Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="2e65d-174">For more information about configuring services and clients, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
 [<span data-ttu-id="2e65d-175">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2e65d-175">\<binding></span></span>](../../../docs/framework/misc/binding.md)  
  
### <a name="the-behaviors-element"></a><span data-ttu-id="2e65d-176">\<Поведения > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-176">The \<behaviors> Element</span></span>  
 <span data-ttu-id="2e65d-177">Это элемент контейнера для элементов `behavior` , задающих поведение службы.</span><span class="sxs-lookup"><span data-stu-id="2e65d-177">This is a container element for the `behavior` elements that define the behaviors for a service.</span></span>  
  
 [<span data-ttu-id="2e65d-178">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="2e65d-178">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a><span data-ttu-id="2e65d-179">\<Поведение > элемент</span><span class="sxs-lookup"><span data-stu-id="2e65d-179">The \<behavior> Element</span></span>  
 <span data-ttu-id="2e65d-180">Каждый элемент `behavior` определяется атрибутом `name` и обеспечивает либо предоставленное системой поведение (например <`throttling`>), либо пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="2e65d-180">Each `behavior` element is identified by a `name` attribute and provides either a system-provided behavior, such as <`throttling`>, or a custom behavior.</span></span> <span data-ttu-id="2e65d-181">Если имя не задано, то элемент behavior будет соответствовать поведению по умолчанию для службы или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2e65d-181">If no name is given then that behavior element corresponds to the default service or endpoint behavior.</span></span>  
  
 [<span data-ttu-id="2e65d-182">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2e65d-182">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a><span data-ttu-id="2e65d-183">Практическое руководство. Конфигурации привязок и поведения</span><span class="sxs-lookup"><span data-stu-id="2e65d-183">How to Use Binding and Behavior Configurations</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="2e65d-184"> упрощает совместный доступ к конфигурациям между конечными точками благодаря использованию системы ссылок в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e65d-184"> makes it easy to share configurations between endpoints using a reference system in configuration.</span></span> <span data-ttu-id="2e65d-185">Вместо того, чтобы непосредственно назначать значения конфигурации для конечной точки, значения конфигурации, относящиеся к привязке, группируются в элементах `bindingConfiguration` в разделе `<binding>` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-185">Rather than directly assigning configuration values to an endpoint, binding-related configuration values are grouped in `bindingConfiguration` elements in the `<binding>` section.</span></span> <span data-ttu-id="2e65d-186">Конфигурация привязок представляет собой именованную группу параметров привязки.</span><span class="sxs-lookup"><span data-stu-id="2e65d-186">A binding configuration is a named group of settings on a binding.</span></span> <span data-ttu-id="2e65d-187">Конечные точки могут ссылаться на `bindingConfiguration` по имени.</span><span class="sxs-lookup"><span data-stu-id="2e65d-187">Endpoints can then reference the `bindingConfiguration` by name.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!—- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint   
          address="myAddress" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint   
          address="myAddress2" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint   
          address="myAddress3" binding="basicHttpBinding"   
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2e65d-188">`name` для `bindingConfiguration` задано в элементе `<binding>` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-188">The `name` of the `bindingConfiguration` is set in the `<binding>` element.</span></span> <span data-ttu-id="2e65d-189">`name` Должен содержать уникальную строку в области типа привязки — в этом случае [< basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), или пустое значение для ссылки на привязку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e65d-189">The `name` must be a unique string within the scope of the binding type—in this case the [<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), or an empty value to refer to the default binding.</span></span> <span data-ttu-id="2e65d-190">Конечная точка содержит ссылки на конфигурацию, задавая для этой строки атрибут `bindingConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="2e65d-190">The endpoint links to the configuration by setting the `bindingConfiguration` attribute to this string.</span></span>  
  
 <span data-ttu-id="2e65d-191">`behaviorConfiguration` реализуется аналогичным образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2e65d-191">A `behaviorConfiguration` is implemented the same way, as illustrated in the following sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint   
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2e65d-192">Заметьте, что в службу добавляет по умолчанию набор поведений службы.</span><span class="sxs-lookup"><span data-stu-id="2e65d-192">Note that the default set of service behaviors are added to the service.</span></span> <span data-ttu-id="2e65d-193">Эта система обеспечивает для конечных точек совместные общие конфигурации, не переопределяя параметры.</span><span class="sxs-lookup"><span data-stu-id="2e65d-193">This system allows endpoints to share common configurations without redefining the settings.</span></span> <span data-ttu-id="2e65d-194">Если требуется область уровня компьютера, создайте конфигурацию привязки или поведения в файле Machine.config. Параметры конфигурации доступны во всех файлах App.config.</span><span class="sxs-lookup"><span data-stu-id="2e65d-194">If machine-wide scope is required, create the binding or behavior configuration in Machine.config. The configuration settings are available in all App.config files.</span></span> <span data-ttu-id="2e65d-195">[Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) упрощает создание конфигураций.</span><span class="sxs-lookup"><span data-stu-id="2e65d-195">The [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) makes it easy to create configurations.</span></span>  
  
## <a name="behavior-merge"></a><span data-ttu-id="2e65d-196">Слияние поведений</span><span class="sxs-lookup"><span data-stu-id="2e65d-196">Behavior Merge</span></span>  
 <span data-ttu-id="2e65d-197">Функция слияния поведений упрощает управление поведениями в ситуациях, когда должен постоянно использоваться набор общих поведений.</span><span class="sxs-lookup"><span data-stu-id="2e65d-197">The behavior merge feature makes it easier to manage behaviors when you want a set of common behaviors to be used consistently.</span></span> <span data-ttu-id="2e65d-198">Эта функция позволяет задавать поведения на разных уровнях иерархии конфигурации, а также настраивать наследование службами поведений от нескольких уровней иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e65d-198">This feature allows you to specify behaviors at different levels of the configuration hierarchy and have services inherit behaviors from multiple levels of the configuration hierarchy.</span></span> <span data-ttu-id="2e65d-199">Проиллюстрируем это следующим образом: предположим, что в IIS имеется следующая структура виртуальных каталогов:</span><span class="sxs-lookup"><span data-stu-id="2e65d-199">To illustrate how this works assume you have the following virtual directory layout in IIS:</span></span>  
  
 <span data-ttu-id="2e65d-200">~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc</span><span class="sxs-lookup"><span data-stu-id="2e65d-200">~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc</span></span>  
  
 <span data-ttu-id="2e65d-201">А файл ~\Web.config содержите следующее:</span><span class="sxs-lookup"><span data-stu-id="2e65d-201">And your ~\Web.config file has the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2e65d-202">Кроме того, имеется дочерний файл Web.config, расположенный в папке ~\Child\Web.config, со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="2e65d-202">And you have a child Web.config located at ~\Child\Web.config with the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2e65d-203">Служба, расположенная в ~\Child\Service.svc, будет действовать таким образом, как будто бы для нее заданы и поведение serviceDebug, и поведение serviceMetadata.</span><span class="sxs-lookup"><span data-stu-id="2e65d-203">The service located at ~\Child\Service.svc will behave as though it has both the serviceDebug and serviceMetadata behaviors.</span></span> <span data-ttu-id="2e65d-204">У службы, расположенной в ~\Service.svc, будет присутствовать только поведение serviceDebug behavior.</span><span class="sxs-lookup"><span data-stu-id="2e65d-204">The service located at ~\Service.svc will only have the serviceDebug behavior.</span></span> <span data-ttu-id="2e65d-205">В этой ситуации две коллекции поведений с одним и тем же именем (в данном случае пустой строкой) объединяются.</span><span class="sxs-lookup"><span data-stu-id="2e65d-205">What happens is that the two behavior collections with the same name (in this case the empty string) are merged.</span></span>  
  
 <span data-ttu-id="2e65d-206">Также можно очищать коллекции поведений с помощью \<снимите > тег и удалять отдельные поведения из коллекции с помощью \<удалить > тег.</span><span class="sxs-lookup"><span data-stu-id="2e65d-206">You can also clear behavior collections by using the \<clear> tag and removed individual behaviors from the collection by using the \<remove> tag.</span></span> <span data-ttu-id="2e65d-207">Например, действие следующих двух конфигураций приведет к тому, что в дочерней службе будет только поведение serviceMetadata:</span><span class="sxs-lookup"><span data-stu-id="2e65d-207">For example, the following two configuration results in the child service having only the serviceMetadata behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2e65d-208">Слияние поведений проводится для безымянных коллекций поведений (как показано выше), а также для именованных коллекций поведений.</span><span class="sxs-lookup"><span data-stu-id="2e65d-208">Behavior merge is done for nameless behavior collections as shown above and named behavior collections as well.</span></span>  
  
 <span data-ttu-id="2e65d-209">Слияние поведений работает в среде размещения IIS, в которой файлы Web.config сливаются в иерархическом порядке с корневыми файлами Web.config и machine.config. Но оно также работает и в среде приложений, где файл machine.config может объединяться с файлом App.config.</span><span class="sxs-lookup"><span data-stu-id="2e65d-209">Behavior merge works in the IIS hosting environment, in which Web.config files merge hierarchically with the root Web.config file and machine.config. But it also works in the application environment, where machine.config can merge with the App.config file.</span></span>  
  
 <span data-ttu-id="2e65d-210">Слияние поведений применяется в конфигурациях как к поведениям конечных точек, так и к поведениям служб.</span><span class="sxs-lookup"><span data-stu-id="2e65d-210">Behavior merge applies to both endpoint behaviors and service behaviors in configuration.</span></span>  
  
 <span data-ttu-id="2e65d-211">Если коллекция дочерних поведений содержит поведение, которое уже определено в коллекции родительских поведений, то дочернее поведение переопределяет родительское.</span><span class="sxs-lookup"><span data-stu-id="2e65d-211">If a child behavior collection contains a behavior that’s already present in the parent behavior collection, the child behavior overrides the parent.</span></span> <span data-ttu-id="2e65d-212">Если коллекция родительских поведений `<serviceMetadata httpGetEnabled="False" />` и Коллекция дочерних поведений содержит `<serviceMetadata httpGetEnabled="True" />`, то дочернее поведение переопределит в коллекции поведений родительское поведение и параметр httpGetEnabled примет значение «true».</span><span class="sxs-lookup"><span data-stu-id="2e65d-212">So if a parent behavior collection had `<serviceMetadata httpGetEnabled="False" />` and a child behavior collection had `<serviceMetadata httpGetEnabled="True" />`, the child behavior would override the parent behavior in the behavior collection and httpGetEnabled would be "true".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e65d-213">См. также</span><span class="sxs-lookup"><span data-stu-id="2e65d-213">See Also</span></span>  
 [<span data-ttu-id="2e65d-214">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="2e65d-214">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="2e65d-215">Настройка приложений Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="2e65d-215">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [<span data-ttu-id="2e65d-216">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="2e65d-216">\<service></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
 [<span data-ttu-id="2e65d-217">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2e65d-217">\<binding></span></span>](../../../docs/framework/misc/binding.md)
