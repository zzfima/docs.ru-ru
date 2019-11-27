---
title: Схема параметров среды выполнения
ms.date: 03/30/2017
helpviewer_keywords:
- schema runtime settings
- configuration schema [.NET Framework], runtime settings
- runtime settings schema
ms.assetid: f04816ab-110d-4e28-9283-845d6d9a4a68
ms.openlocfilehash: d5af9f3299b48d431b43566c11610d745167b60b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431056"
---
# <a name="run-time-settings-schema"></a>Схема параметров среды выполнения

Параметры времени выполнения используются средой CLR для настройки приложений, предназначенных для .NET Framework.

## <a name="the-runtime-section-and-its-parent-and-child-elements"></a>Раздел > среды выполнения \<и его родительские и дочерние элементы

[\<configuration>](../configuration-element.md)\
[> среды выполнения\<](runtime-element.md) &nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;[\<алвайсфловимперсонатионполици >](alwaysflowimpersonationpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<AppContextSwitchOverrides >](appcontextswitchoverrides-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<аппдомаинманажерассембли >](appdomainmanagerassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<аппдомаинманажертипе >](appdomainmanagertype-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<аппдомаинресаурцемониторинг >](appdomainresourcemonitoring-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyBinding >](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<dependentAssembly >](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyIdentity >](assemblyidentity-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<bindingRedirect >](bindingredirect-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<codeBase >](codebase-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<publisherpolicy apply >](publisherpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[зондирование](probing-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<qualifyAssembly >](qualifyassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<тег supportportability >](supportportability-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<элемент bypasstrustedappstrongnames >](bypasstrustedappstrongnames-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<компатсортнлсверсион >](compatsortnlsversion-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<developmentMode >](developmentmode-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCachingBindingFailures >](disablecachingbindingfailures-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<дисаблекоммитсреадстакк >](disablecommitthreadstack-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<дисаблефусионупдатесфромадманажер >](disablefusionupdatesfromadmanager-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<енаблеампмпарсеаджустмент >](enableampmparseadjustment-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<енфорцефипсполици >](enforcefipspolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<етвенабле >](etwenable-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<форцеперформанцекаунтеруникуешаредмемориреадс >](forceperformancecounteruniquesharedmemoryreads-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcAllowVeryLargeObjects >](gcconcurrent-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcConcurrent >](gcconcurrent-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<гккпуграуп >](gccpugroup-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<гчеапаффинитиземаск >](gcheapaffinitizemask-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<гчеапкаунт >](gcheapcount-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<гклохсрешолд >](gclohthreshold-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<гкноаффинитизе >](gcnoaffinitize-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcServer >](gcserver-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<generatePublisherEvidence >](generatepublisherevidence-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<легацикорруптедстатиксцептионсполици >](legacycorruptedstateexceptionspolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<легациимперсонатионполици >](legacyimpersonationpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<лоадфромремотесаурцес >](loadfromremotesources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx40_LegacySecurityPolicy](netfx40-legacysecuritypolicy-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx40_PInvokeStackResilience](netfx40-pinvokestackresilience-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings](netfx45-cultureawarecomparergethashcode-longstrings-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[\<преферкоминстеадофманажедремотинг >](prefercominsteadofmanagedremoting-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<relativeBindForResources >](relativebindforresources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<элемент shadowcopyverifybytimestamp >](shadowcopyverifybytimestamp-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<Thread_UseAllCpuGroups](thread-useallcpugroups-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[\<сровунобсерведтаскексцептионс >](throwunobservedtaskexceptions-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<TimeSpan_LegacyFormatMode](runtime-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[\<элемент uselegacyjit >](uselegacyjit-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseRandomizedStringHashAlgorithm >](userandomizedstringhashalgorithm-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<усесмаллинтерналсреадстаккс >](usesmallinternalthreadstacks-element.md)\
&nbsp;&nbsp;[\<System. Runtime. caching >](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<memoryCache >](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<намедкачес >](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<добавить >](add-element-for-namedcaches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clear >](clear-element-for-namedcaches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<удалить >](remove-element-for-namedcaches.md)

## <a name="alphabetical-list-of-runtime-elements"></a>Алфавитный список элементов > среды выполнения \<

|Элемент|Описание|
|-------------|-----------------|
|[\<add>](add-element-for-namedcaches.md)|Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|Определяет один или несколько коммутаторов, используемых классом <xref:System.AppContext> для предоставления механизма отказа от новых функциональных возможностей.|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|
|[\<assemblyIdentity>](assemblyidentity-element-for-runtime.md)|Содержит идентификационные сведения о сборке.|
|[\<bindingRedirect>](bindingredirect-element.md)|Перенаправляет одну версию сборки на другую.|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|Указывает, следует ли обходить проверку строгих имен для доверенных сборок.|
|[\<clear>](clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|
|[\<codeBase>](codebase-element.md)|Указывает, где среда выполнения может найти сборку.|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Указывает, что при операциях сравнения строк среда выполнения должна использовать устаревший режим сортировки.|
|[\<dependentAssembly>](dependentassembly-element.md)|Инкапсулирует политику привязки и расположение каждой сборки.|
|[\<developmentMode>](developmentmode-element.md)|Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Указывает, отключено ли кэширование ошибок привязки, что является поведением по умолчанию в .NET Framework 2,0.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Указывает, фиксируется ли весь стек потоков при запуске потока.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Определяет, используют ли методы анализа даты и времени скорректированной набор правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Указывает, нужно ли принудительно обеспечивать соблюдение требования конфигурации компьютера о том, что криптографические алгоритмы должны соответствовать стандартам FIPS.|
|[\<etwEnable>](etwenable-element.md)|Указывает, следует ли включить трассировку событий Windows для событий среды CLR.|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Указывает, выполняет ли среда выполнения сборку мусора параллельно.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Определяет, поддерживает ли сборка мусора несколько групп ЦП.|
|[\<Гчеапаффинитиземаск >](gcheapaffinitizemask-element.md)|Определяет сходство между кучами сборщика мусора и отдельными процессорами.|
|[\<Гчеапкаунт >](gcheapcount-element.md)|Указывает число куч/потоков, используемых для сборки мусора сервера.  |
|[\<Гклохсрешолд >](gclohthreshold-element.md)|Указывает пороговый размер, который приводит к тому, что объекты попадают в кучу больших объектов (LOH).|
|[\<Гкноаффинитизе >](gcnoaffinitize-element.md)|Указывает, следует ли привязать потоки сервера GC с ЦП.|
|[\<gcServer>](gcserver-element.md)|Указывает, выполняет ли среда CLR сборку мусора сервера.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Указывает, использует ли среда выполнения политику разграничения доступа кода, используемую издателем.|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Указывает, позволяет ли среда выполнения управляемому коду перехватывать нарушения прав доступа и другие исключения поврежденного состояния.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Указывает, загружены ли сборки из удаленных источников как полностью доверенные.|
|[\<memoryCache>](memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для экземпляра `namedCache` .|
|[\<NetFx40_LegacySecurityPolicy >](netfx40-legacysecuritypolicy-element.md)|Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.|
|[\<NetFx40_PInvokeStackResilience >](netfx40-pinvokestackresilience-element.md)|Указывает, исправляет ли автоматически среда выполнения неправильные объявления вызова неуправляемого кода во время выполнения за счет скорости перехода между управляемыми и неуправляемым кодом.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Определяет, использует ли среда выполнения постоянный объем памяти для вычисления хэш-кодов методом <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|
|[\<PreferComInsteadOfManagedRemoting>](prefercominsteadofmanagedremoting-element.md)|Указывает, что среда выполнения должна использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.|
|[\<probing>](probing-element.md)|Задает вложенные папки, в которых среда выполняет поиск при загрузке сборок.|
|[\<publisherPolicy>](publisherpolicy-element.md)|Указывает, применяет ли среда выполнения политику издателя.|
|[\<qualifyAssembly>](qualifyassembly-element.md)|Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Оптимизирует поиск вспомогательных сборок.|
|[\<remove>](remove-element-for-namedcaches.md)|Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.|
|[\<runtime>](runtime-element.md)|Содержит сведения о привязке сборок и поведении при сборке мусора.|
|[\<shadowCopyTimeStampVerification>](shadowcopyverifybytimestamp-element.md)|Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленное в .NET Framework 4, или возвращается к поведению при запуске более ранних версий .NET Framework.|
|[\<supportPortability>](supportportability-element.md)|Указывает, что приложение может ссылаться на ту же сборку в двух различных реализациях .NET Framework, отключая поведение по умолчанию, которое рассматривает сборки как эквивалент для переносимости приложения.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Указывает сведения о конфигурации кэша объектов в памяти, используемого по умолчанию.|
|[\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)|Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.|
|[\<TimeSpan_LegacyFormatMode >](runtime-element.md)|Указывает, использует ли среда выполнения устаревшее форматирование для значений <xref:System.TimeSpan>.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Определяет, использует ли среда CLR устаревший 64-разрядный JIT-компилятор для JIT-компиляции.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Указывает, вычисляет ли среда выполнения хэш-коды для строк для каждого домена приложения.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Запрашивает использование средой выполнения явных размеров стека при создании определенных потоков, используемых для внутренних целей, вместо размер стека по умолчанию.|

## <a name="see-also"></a>См. также:

- [Схема файла конфигурации](../index.md)
- [Отключение параллельной сборки мусора](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Перенаправление версий сборки](../../redirect-assembly-versions.md)
