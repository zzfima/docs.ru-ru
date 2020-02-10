---
title: Блокировка безопасности PII
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: 56c8acbe53f1e0243f7c679da6ef04f7135bcd3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094973"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="db34a-102">Блокировка безопасности PII</span><span class="sxs-lookup"><span data-stu-id="db34a-102">PII Security Lockdown</span></span>
<span data-ttu-id="db34a-103">В этом примере показано, как управлять несколькими связанными с безопасностью компонентами службы Windows Communication Foundation (WCF) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="db34a-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
- <span data-ttu-id="db34a-104">Шифрование конфиденциальных сведений в файле конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="db34a-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
- <span data-ttu-id="db34a-105">Блокировка элементов файла конфигурации службы, не позволяющая переопределять параметры во вложенных подкаталогах службы.</span><span class="sxs-lookup"><span data-stu-id="db34a-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
- <span data-ttu-id="db34a-106">Управление отображением персональных данных в трассировках и журналах сообщений.</span><span class="sxs-lookup"><span data-stu-id="db34a-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="db34a-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db34a-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="db34a-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="db34a-108">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="db34a-109">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="db34a-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="db34a-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="db34a-110">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="db34a-111">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="db34a-111">Discussion</span></span>  
 <span data-ttu-id="db34a-112">С помощью этих функций можно управлять безопасностью службы, используя их вместе либо по отдельности.</span><span class="sxs-lookup"><span data-stu-id="db34a-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="db34a-113">Это не является основным руководством по обеспечению безопасности службы WCF.</span><span class="sxs-lookup"><span data-stu-id="db34a-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="db34a-114">Файлы конфигурации .NET Framework могут содержать конфиденциальную информацию, например строки подключения, используемые для подключения к базам данных.</span><span class="sxs-lookup"><span data-stu-id="db34a-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="db34a-115">При размещении на веб-сервере с общим доступом может потребоваться зашифровать эту информацию в файле конфигурации службы, чтобы защитить ее от просмотра стандартными средствами.</span><span class="sxs-lookup"><span data-stu-id="db34a-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="db34a-116">В платформе .NET Framework 2.0 и более поздних версиях предусмотрена возможность шифрования разделов файла конфигурации с помощью API защиты данных Windows (DPAPI) или поставщика служб шифрования RSA.</span><span class="sxs-lookup"><span data-stu-id="db34a-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="db34a-117">Приложение aspnet_regiis.exe, использующее DPAPI или RSA, позволяет зашифровать указанные разделы файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db34a-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="db34a-118">При размещении на веб-сервере можно реализовывать службы в подкаталогах других служб.</span><span class="sxs-lookup"><span data-stu-id="db34a-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="db34a-119">Семантика определения значений параметров конфигурации, используемая по умолчанию, позволяет переопределять в файлах конфигурации, расположенных во вложенных каталогах, значения параметров конфигурации, указанные в родительском каталоге.</span><span class="sxs-lookup"><span data-stu-id="db34a-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="db34a-120">В некоторых ситуациях это может быть нежелательно по различным причинам.</span><span class="sxs-lookup"><span data-stu-id="db34a-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="db34a-121">Конфигурация службы WCF поддерживает блокировку значений конфигурации, чтобы вложенная конфигурация создавала исключения при выполнении вложенной службы с переопределенными значениями конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db34a-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="db34a-122">В этом образце демонстрируется, как при трассировке и ведении журналов сообщений управлять регистрацией персональных данных (PII), например имен пользователей и паролей.</span><span class="sxs-lookup"><span data-stu-id="db34a-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="db34a-123">По умолчанию регистрация личной информации отключена. Впрочем, в некоторых ситуациях ее требуется включить в целях отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="db34a-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="db34a-124">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="db34a-124">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="db34a-125">Кроме того, в нем используется аналогичная система трассировки и журнала сообщений.</span><span class="sxs-lookup"><span data-stu-id="db34a-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="db34a-126">Дополнительные сведения см. в примере [трассировки и регистрации сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="db34a-126">For more information, see the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="db34a-127">Шифрование элементов файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="db34a-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="db34a-128">При размещении службы на веб-сервере с общим доступом может потребоваться зашифровать некоторые элементы файла конфигурации в целях безопасности, например строки для подключения к базам данных, в которых может содержаться конфиденциальная информация.</span><span class="sxs-lookup"><span data-stu-id="db34a-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="db34a-129">Элемент конфигурации может быть зашифрован с помощью средства aspnet_regiis. exe, находящихся в папке .NET Framework например,%WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span><span class="sxs-lookup"><span data-stu-id="db34a-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="db34a-130">Шифрование значений в разделе appSettings файла Web.config для данного образца</span><span class="sxs-lookup"><span data-stu-id="db34a-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1. <span data-ttu-id="db34a-131">Откройте командную строку с помощью команды Start-> выполнить....</span><span class="sxs-lookup"><span data-stu-id="db34a-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="db34a-132">Введите `cmd` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="db34a-132">Type in `cmd` and click **OK**.</span></span>  
  
2. <span data-ttu-id="db34a-133">Перейдите в каталог текущей версии .NET Framework с помощью следующей команды: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span><span class="sxs-lookup"><span data-stu-id="db34a-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3. <span data-ttu-id="db34a-134">Зашифруйте параметры конфигурации appSettings в папке Web.config с помощью следующей команды: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span><span class="sxs-lookup"><span data-stu-id="db34a-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="db34a-135">Дополнительные сведения о шифровании разделов файлов конфигурации можно найти в разделе "инструкции по DPAPI" в конфигурации ASP.NET ([Создание безопасных приложений ASP.NET: проверка подлинности, авторизация и безопасное взаимодействие](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) и инструкции по RSA в конфигурации ASP.NET ([инструкции: Шифрование разделов конфигурации в ASP.NET 2,0 с помощью RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span><span class="sxs-lookup"><span data-stu-id="db34a-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="db34a-136">Блокировка элементов файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="db34a-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="db34a-137">При размещении на веб-сервере можно реализовывать службы в подкаталогах служб.</span><span class="sxs-lookup"><span data-stu-id="db34a-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="db34a-138">В таких ситуациях значения параметров конфигурации службы, содержащейся в подкаталоге, вычисляются на основании значений из файла Machine.config, которые затем объединяются со значениями из файлов Web.config, расположенных во вложенных папках ниже в дереве каталогов, и наконец с файлом Web.config из каталога, в котором содержится служба.</span><span class="sxs-lookup"><span data-stu-id="db34a-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="db34a-139">В поведении по умолчанию для большинства элементов конфигурации разрешено переопределение значений, заданных в файлах конфигурации в родительских каталогах, значениями из файлов конфигурации во вложенных подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="db34a-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="db34a-140">В некоторых случаях имеет смысл запретить такую возможность.</span><span class="sxs-lookup"><span data-stu-id="db34a-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="db34a-141">В платформе .NET Framework предусмотрен способ блокировки элементов файла конфигурации, чтобы при попытке переопределить такие элементы во время выполнения выдавались исключения.</span><span class="sxs-lookup"><span data-stu-id="db34a-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="db34a-142">Можно заблокировать элемент конфигурации, указав атрибут `lockItem` для узла файла конфигурации. Например, если заблокировать узел CalculatorServiceBehavior в файле конфигурации, файлы конфигурации служб калькулятора из вложенных каталогов не смогут изменять поведение. Для этого можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="db34a-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>   
          <serviceBehaviors>   
             <behavior name="CalculatorServiceBehavior" lockItem="true">   
               <serviceMetadata httpGetEnabled="True"/>   
               <serviceDebug includeExceptionDetailInFaults="False" />   
             </behavior>   
          </serviceBehaviors>   
       </behaviors>   
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="db34a-143">Блокировка элементов конфигурации может быть более конкретной.</span><span class="sxs-lookup"><span data-stu-id="db34a-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="db34a-144">Можно заблокировать набор элементов в коллекции подэлементов, указав их список в виде значения атрибута `lockElements`.</span><span class="sxs-lookup"><span data-stu-id="db34a-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="db34a-145">Можно заблокировать набор атрибутов элемента, указав их список в виде значения атрибута `lockAttributes`.</span><span class="sxs-lookup"><span data-stu-id="db34a-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="db34a-146">Можно заблокировать всю коллекцию элементов или атрибутов, кроме содержащихся в определенном списке, указав его в виде значения атрибута `lockAllElementsExcept` или `lockAllAttributesExcept` для узла.</span><span class="sxs-lookup"><span data-stu-id="db34a-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="db34a-147">Конфигурация регистрации персональных данных (PII)</span><span class="sxs-lookup"><span data-stu-id="db34a-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="db34a-148">Регистрация персональных данных управляется двумя параметрами: действующим для всего компьютера (в файле Machine.config), позволяющим администратору этого компьютера разрешать и запрещать регистрацию персональных данных, и параметром приложения, предоставляющим администратору этого приложения возможность разрешать и запрещать регистрацию таких данных для каждого источника в файле Web.config или App.config.</span><span class="sxs-lookup"><span data-stu-id="db34a-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="db34a-149">Параметр на уровне компьютера управляется путем установки `enableLoggingKnownPii` в значение `true` или `false`в элементе `machineSettings` в файле Machine. config. Например, следующий пример позволяет приложениям включить ведение журнала личных данных.</span><span class="sxs-lookup"><span data-stu-id="db34a-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="db34a-150">Расположение по умолчанию для файла Machine.config: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="db34a-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="db34a-151">Если в файле Machine.config отсутствует атрибут `enableLoggingKnownPii`, регистрация персональных данных запрещена.</span><span class="sxs-lookup"><span data-stu-id="db34a-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="db34a-152">Регистрация персональных данных для приложения регулируется значением атрибута `logKnownPii` исходного элемента: `true` или `false` (в файле Web.config или App.config).</span><span class="sxs-lookup"><span data-stu-id="db34a-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="db34a-153">Например, следующая конфигурация разрешает регистрацию персональных данных как в журналах сообщений, так и в журналах трассировок.</span><span class="sxs-lookup"><span data-stu-id="db34a-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>   
                ...   
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...   
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="db34a-154">Если атрибут `logKnownPii` не указан, регистрация персональных данных отключена.</span><span class="sxs-lookup"><span data-stu-id="db34a-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="db34a-155">Персональные данные регистрируются только если атрибут `enableLoggingKnownPii` имеет значение `true`, и атрибут `logKnownPii` также имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="db34a-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db34a-156">Модуль System.Diagnostics игнорирует все атрибуты всех источников, за исключением приведенного в файле конфигурации первым.</span><span class="sxs-lookup"><span data-stu-id="db34a-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="db34a-157">Добавление атрибута `logKnownPii` во второй источник в файле конфигурации не на что не повлияет.</span><span class="sxs-lookup"><span data-stu-id="db34a-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="db34a-158">Для выполнения этого примера потребуется изменить файл Machine.config вручную. Необходимо соблюдать осторожность при изменении этого файла, поскольку неправильные значения и синтаксические ошибки могут сделать невозможной работу всех приложений на базе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db34a-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="db34a-159">Также можно зашифровывать элементы файла конфигурации с помощью DPAPI и RSA.</span><span class="sxs-lookup"><span data-stu-id="db34a-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="db34a-160">Дополнительные сведения см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="db34a-160">For more information, see the following links:</span></span>  
  
- <span data-ttu-id="db34a-161">[Создание безопасных приложений ASP.NET: проверка подлинности, авторизация и безопасное взаимодействие](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="db34a-161">[Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span></span>  
  
- <span data-ttu-id="db34a-162">[Инструкции. Шифрование разделов конфигурации в ASP.NET 2,0 с помощью RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="db34a-162">[How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="db34a-163">Настройка, построение и выполнение примера</span><span class="sxs-lookup"><span data-stu-id="db34a-163">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="db34a-164">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="db34a-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="db34a-165">Измените файл Machine.config, присвоив атрибуту `enableLoggingKnownPii` значение `true` и добавив родительские узлы при необходимости.</span><span class="sxs-lookup"><span data-stu-id="db34a-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3. <span data-ttu-id="db34a-166">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="db34a-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="db34a-167">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="db34a-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="db34a-168">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="db34a-168">To clean up the sample</span></span>  
  
1. <span data-ttu-id="db34a-169">Измените файл Machine.config, присвоив атрибуту `enableLoggingKnownPii` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="db34a-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db34a-170">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="db34a-170">See also</span></span>

- <span data-ttu-id="db34a-171">[Примеры мониторинга AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="db34a-171">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
