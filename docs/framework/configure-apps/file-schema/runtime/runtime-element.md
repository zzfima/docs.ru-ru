---
title: "Элемент &lt;runtime&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<runtime> - элемент"
  - "теги контейнеров, <runtime> - элемент"
  - "runtime - элемент"
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
caps.latest.revision: 70
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 62
---
# Элемент &lt;runtime&gt;
Элемент, содержащий сведения о привязке сборок и сборке мусора.  
  
## Синтаксис  
  
```  
<runtime>  
</runtime>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<alwaysFlowImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Указывает, что идентификация Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.|  
|[\<appDomainManagerAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Задает сборку, предоставляющую диспетчер домена приложения для домена приложения по умолчанию в процессе.|  
|[\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Задает тип, выполняющий функции диспетчера домена приложения для домена приложения по умолчанию.|  
|[\<appDomainResourceMonitoring\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Указывает среде выполнения собирать статистические данные по всем доменам приложений в процессе за весь период существования процесса.|  
|[\<assemblyBinding\>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Содержит сведения о перенаправлении версии сборки и о расположении сборок.|  
|[\<bypassTrustedAppStrongNames\>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Определяет необходимость пропуска проверки строгих имен для доверенных сборок.|  
|[\<CompatSortNLSVersion\>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Указывает, что среда выполнения должна использовать устаревшее поведение сортировки при выполнении сравнений строк.|  
|[\<developmentMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Указывает, будет ли среда выполнять поиск сборок в папках, заданных в переменной среды DEVPATH.|  
|[\<disableCachingBindingFailures\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Указывает, заблокировано ли кэширование привязки ошибок, которое по умолчанию выполняется в платформе .NET Framework версии 2.0.|  
|[\<disableCommitThreadStack\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Указывает, сразу ли выделяется память, необходимая для хранения полного стека потока, при запуске этого потока.|  
|[\<disableFusionUpdatesFromADManager\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Задает, отключено ли поведение по умолчанию, которое разрешает хост\-приложению среды выполнения переопределять параметры конфигурации для домена приложения.|  
|[\<enforceFIPSPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Указывает, следует ли включить обязательное исполнение требования конфигурации компьютера, чтобы криптографические алгоритмы соответствовали FIPS.|  
|[\<etwEnable\>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Указывает, следует ли включать отслеживание событий для Windows \(трассировка событий Windows\) для событий среды CLR.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads\>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Указывает, использует ли PerfCounter.dll параметр реестра CategoryOptions в приложениях .NET Framework 1.1 для определения необходимости загрузки данных счетчиков производительности из общей памяти конкретной категории или глобальной памяти.|  
|[\<gcAllowVeryLargeObjects\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|На 64 разрядных платформах, позволяет использовать массивы, размер которых превышает 2 гигабайта \(GB\).|  
|[\<gcConcurrent\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Указывает, будет ли среда CLR производить параллельную сборку мусора.|  
|[\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Определяет, поддерживает ли сборка мусора несколько групп ЦП.|  
|[\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Указывает, будет ли среда CLR производить сборку мусора сервера.|  
|[\<generatePublisherEvidence\>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Указание того, использует ли среда выполнения политику издателя по управлению доступом для кода \(CAS\).|  
|[\<legacyCorruptedStateExceptionsPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Задает, разрешает ли среда CLR управляемому коду перехватывать нарушения прав доступа и другие исключения поврежденного состояния.|  
|[\<legacyImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.|  
|[\<loadfromRemoteSources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Указывает, следует ли все сборки с удаленных источников загружать с полным доверием.|  
|[\<NetFx40\_LegacySecurityPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Определяет, использует ли среда выполнения политику разграничения доступа кода \(CAS\) прежних версий.|  
|[\<NetFx40\_PInvokeStackResilience\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Указывает, будет ли среда выполнения автоматически исправлять неверные объявления вызова неуправляемого кода за счет более медленных переходов между управляемым и неуправляемым кодом.|  
|[\<NetFx45\_CultureAwareComparerGetHashCode\_LongStrings\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Определяет, использует ли среда выполнения фиксированный объем памяти для вычисления хэш\-кода для метода <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>.|  
|[\<PreferComInsteadOfRemoting\>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Указывает, будет ли среда выполнения использовать COM\-взаимодействие вместо удаленного взаимодействия за пределами границ домена приложения.|  
|[\<relativeBindForResources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Оптимизирует поиск вспомогательных сборок.|  
|[\<shadowCopyVerifyByTimeStamp\>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Указывает, используется ли при теневом копировании поведение при запуске по умолчанию, введенное в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], или осуществляется возврат к поведению при запуске, имевшему место в предыдущих версиях платформы .NET Framework.|  
|[\<supportPortability\>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Указывает, что приложение может ссылаться на одну и ту же сборку в двух различных реализациях платформы .NET Framework путем отключения поведения по умолчанию, в котором в целях переносимости приложений эти сборки трактуются как эквивалентные.|  
|[\<system.runtime.caching\>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Предоставляет сведения о конфигурации для объекта кэша в памяти по умолчанию.|  
|[\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Определяет, распределяет ли среда выполнения управляемые потоки по всем группам ЦП.|  
|[\<ThrowUnobservedTaskExceptions\>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.|  
|[\<TimeSpan\_LegacyFormatMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Указывает, использует ли среда выполнения устаревшее форматирование для значений <xref:System.TimeSpan>.|  
|[\<UseRandomizedStringHashAlgorithm\>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Указывает, вычисляет ли среда выполнения хэш\-коды для строк для каждого домена приложения.|  
|[\<UseSmallInternalThreadStacks\>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Запрашивает использование средой выполнения явных размеров стека вместо размеров стека по умолчанию, когда создает определенные потоки, используемые на внутреннем уровне.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
  
## Заметки  
 В .NET Framework версии 2.0 олицетворенное удостоверение проходит через асинхронные точки в домене приложения.  В .NET Framework версии 2.0 можно включать или отключать прохождение олицетворения через асинхронные точки, конфигурируя должным образом элемент среды выполнения в файле machine.config или в файле конфигурации приложения.  Для ASP.NET поток олицетворения можно конфигурировать в файле aspnet.config, находящемся в папке \<Windows Folder\>\\Microsoft.NET\\Framework\\vx.x.xxxx.  
  
 По умолчанию ASP.NET отключает поток олицетворения в файле aspnet.config, используя следующие параметры конфигурации:  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 В ASP.NET, если вместо этого существует намерение разрешить поток олицетворения, то необходимо явно использовать следующие параметры конфигурации:  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
 Дополнительные сведения см. в разделах [Элемент \<legacyImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) и [Элемент \<alwaysFlowImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## Пример  
 В следующем примере показан способ перенаправления одной версии сборки на другую.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
             <bindingRedirect oldVersion="1.0.0.0"  
                              newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/ru-ru/ba2c6c67-5778-497c-9fac-5f793b5500c7)