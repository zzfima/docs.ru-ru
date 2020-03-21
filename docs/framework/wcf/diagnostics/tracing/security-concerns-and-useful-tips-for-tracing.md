---
title: Проблемы безопасности и полезные советы при трассировке
ms.date: 03/30/2017
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
ms.openlocfilehash: 5ced4f3a3a5e83564703db88b28ee2b3c6eeb1a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185719"
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="eaa0c-102">Проблемы безопасности и полезные советы при трассировке</span><span class="sxs-lookup"><span data-stu-id="eaa0c-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="eaa0c-103">В этом разделе описываются способы защиты конфиденциальных сведений от раскрытия, а также приводятся полезные советы по использованию WebHost.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="eaa0c-104">Использование пользовательского прослушивателя трассировки с WebHost</span><span class="sxs-lookup"><span data-stu-id="eaa0c-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="eaa0c-105">При разработке прослушивателя трассировки следует учитывать возможность потери трассировок, если служба размещена на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="eaa0c-106">При перезапуске WebHost выполняемый процесс отключается, и его место занимает дубликат.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="eaa0c-107">Впрочем, оба процесса должны иметь доступ к одному и тому же ресурсу в течение некоторого времени, в зависимости от типа прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="eaa0c-108">В этом случае `XmlWriterTraceListener` создает новый файл трассировки для второго процесса, тогда как трассировка событий Windows управляет несколькими процессами в пределах одного сеанса и предоставляет доступ к одному и тому же файлу.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="eaa0c-109">Если разрабатываемый прослушиватель не обладает аналогичными функциональными возможностями, возможна потеря трассировок, когда файл заблокирован двумя процессами.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="eaa0c-110">Также следует учитывать, что пользовательский прослушиватель трассировки может отправлять трассировки и сообщения по сети, например в удаленную базу данных.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="eaa0c-111">Специалисту, выполняющему развертывание приложения, следует правильно настроить управление доступом для пользовательских прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="eaa0c-112">Также следует обеспечить управление безопасностью для всей личной информации, потенциально доступной из удаленного расположения.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="eaa0c-113">Регистрация конфиденциальных сведений</span><span class="sxs-lookup"><span data-stu-id="eaa0c-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="eaa0c-114">Трассировки содержат заголовки сообщений, когда сообщения находятся в области действия.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="eaa0c-115">Когда трассировка включена, персональные данные в заголовках, зависящих от приложения (такие как строка запроса), и в теле сообщения (такие как номер кредитной карты) могут быть видимы в журналах.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="eaa0c-116">За надлежащее управление доступом к файлам конфигурации и трассировки отвечает специалист, выполняющий развертывание приложения.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="eaa0c-117">Если требуется, чтобы подобные сведения не были видимы, необходимо отключить трассировку или фильтровать часть данных (если предполагается доступ к трассировкам других лиц).</span><span class="sxs-lookup"><span data-stu-id="eaa0c-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="eaa0c-118">Следующие советы помогут предотвратить непреднамеренное раскрытие содержимого файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
- <span data-ttu-id="eaa0c-119">Убедитесь, что файлы журналов защищены с помощью списков управления доступом (ACL), как в сценарии с использованием WebHost, так и в сценарии с резидентной службой.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
- <span data-ttu-id="eaa0c-120">Выберите расширение файла, которое нельзя легко получить с помощью веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="eaa0c-121">Например, расширение XML безопасным не является.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="eaa0c-122">Список расширений, которые могут быть получены, можно найти в руководстве по администрированию IIS.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
- <span data-ttu-id="eaa0c-123">Задайте абсолютный путь к местоположению файла журнала, которое должно находиться за пределами общедоступного каталога vroot WebHost во избежание доступа к нему третьих лиц с помощью веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="eaa0c-124">По умолчанию ключи и персональные данные (personally identifiable information, PII), такие как имя пользователя и пароль, не регистрируются трассировкой и не указываются в заносимых в журнал сообщениях.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="eaa0c-125">Тем не менее, администратор компьютера может с помощью атрибута `enableLoggingKnownPII` в элементе `machineSettings` файла Machine.config разрешить приложениям, выполняющимся на компьютере, регистрировать известные персональные данные (PII). Это делается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eaa0c-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>
```  
  
 <span data-ttu-id="eaa0c-126">Специалист, выполняющий развертывание приложения, может затем с помощью атрибута `logKnownPii` в файле App.config или Web.config включить регистрацию персональных данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eaa0c-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="eaa0c-127">Регистрация PII включена, только когда оба параметра имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="eaa0c-128">Такое сочетание из двух ключей позволяет регистрировать известные PII для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="eaa0c-129">Необходимо иметь в виду, что при задании в файле конфигурации двух или более пользовательских источников считываются только атрибуты первого источника.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="eaa0c-130">Остальные атрибуты не учитываются.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-130">The others are ignored.</span></span> <span data-ttu-id="eaa0c-131">Это значит, что в случае следующего файла App.config PII не регистрируются для обоих источников, несмотря на то что для второго источника явно включена регистрация персональных данных.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="false">  
        <listeners>  
           <add name="messages"  
                type="System.Diagnostics.XmlWriterTraceListener"  
                initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
      <source name="System.ServiceModel"
         logKnownPii="true">  
         <listeners>  
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="eaa0c-132">Если элемент `<machineSettings enableLoggingKnownPii="Boolean"/>`<xref:System.Configuration.ConfigurationErrorsException> присутствует за пределами файла Machine.config, система вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="eaa0c-133">Изменения вступают в силу только после запуска или перезапуска приложения.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="eaa0c-134">Когда оба атрибута имеют значение `true`, при запуске регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="eaa0c-135">Событие также регистрируется, если атрибут `logKnownPii` имеет значение `true`, а атрибут `enableLoggingKnownPii` имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="eaa0c-136">Для получения дополнительной информации [PII Security Lockdown](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) о регистрации PII см.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-136">For more information on PII logging, see [PII Security Lockdown](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="eaa0c-137">Администратор компьютера и специалист, выполняющий развертывание приложения, должны быть предельно осторожными при использовании этих двух переключателей.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="eaa0c-138">Если регистрация PII включена, ключи контроля доступа и персональные данные заносятся в журналы.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="eaa0c-139">Если она отключена, конфиденциальные и зависящие от приложения данные все равно регистрируются в составе заголовков и тел сообщений.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="eaa0c-140">Для более тщательного обсуждения конфиденциальности и защиты PII от [разоблачения, см.](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="eaa0c-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="eaa0c-141">Кроме того, IP-адрес отправителя сообщения регистрируется при каждом подключении в случае транспорта, ориентированного на подключения, а в остальных случаях - при каждом сообщении.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="eaa0c-142">Это делается без согласия отправителя.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="eaa0c-143">Впрочем, эта регистрация выполняется только на уровнях трассировки «Данные» и «Подробно», которые не используются по умолчанию и не рекомендуются для использования в производственной среде, за исключением отладки.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa0c-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eaa0c-144">See also</span></span>

- [<span data-ttu-id="eaa0c-145">Трассировки</span><span class="sxs-lookup"><span data-stu-id="eaa0c-145">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
