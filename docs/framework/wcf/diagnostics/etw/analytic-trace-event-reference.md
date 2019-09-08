---
title: Ссылка на событие аналитического отслеживания
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF]. reference
ms.assetid: e44540cf-44a1-4efc-b965-7fbfd2131d73
ms.openlocfilehash: 1b44e6b0abf0fc48b43ae17cbd24780e46ae518d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798128"
---
# <a name="analytic-trace-event-reference"></a>Ссылка на событие аналитического отслеживания
В следующей таблице определены уровни событий, идентификаторы и сообщения, связанные с аналитической трассировкой WCF.  
  
## <a name="event-reference"></a>Ссылка на событие  
  
|Идентификатор события|Уровень события|Сообщение о событии|Ключевые слова|  
|--------------|-----------------|-------------------|--------------|  
|[131 — BufferPoolAllocation](131-bufferpoolallocation.md)|Verbose|Выделение %1 байт пулом.|Инфраструктура|  
|[132 — BufferPoolChangeQuota](132-bufferpoolchangequota.md)|Verbose|BufferPool размером %1, изменение квоты на %2.|Инфраструктура|  
|[133 — ActionItemScheduled](133-actionitemscheduled.md)|Verbose|Вызван обратный вызов планировщика потока ввода-вывода.|Инфраструктура|  
|[134 — ActionItemCallbackInvoked](134-actionitemcallbackinvoked.md)|Verbose|Вызван обратный вызов планировщика потока ввода-вывода.|Инфраструктура|  
|[201 — ClientMessageInspectorAfterReceiveInvoked](201-clientmessageinspectorafterreceiveinvoked.md)|Сведения|Диспетчер вызвал AfterReceiveReply относительно ClientMessageInspector типа «%1».|Troubleshooting, ServiceModel|  
|[202 — ClientMessageInspectorBeforeSendInvoked](202-clientmessageinspectorbeforesendinvoked.md)|Сведения|Диспетчер вызвал BeforeSendRequest для ClientMessageInspector типа «%1».|Troubleshooting, ServiceModel|  
|[203 — ClientParameterInspectorAfterCallInvoked](203-clientparameterinspectoraftercallinvoked.md)|Сведения|Диспетчер вызвал метод «AfterCall» для объекта ClientParameterInspector. типа «%1».|Troubleshooting, ServiceModel|  
|[204 — ClientParameterInspectorBeforeCallInvoked](204-clientparameterinspectorbeforecallinvoked.md)|Сведения|Диспетчер вызвал BeforeCall для ClientParameterInspector типа «%1».|Troubleshooting, ServiceModel|  
|[205 — OperationInvoked](205-operationinvoked.md)|Сведения|OperationInvoker вызвал метод «%1».|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[206 — ErrorHandlerInvoked](206-errorhandlerinvoked.md)|Сведения|The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.  ErrorHandled == '%2'.|Troubleshooting, ServiceModel|  
|[207 — FaultProviderInvoked](207-faultproviderinvoked.md)|Сведения|Диспетчер вызвал FaultProvider типа «%1» с исключением типа «%2».|Troubleshooting, ServiceModel|  
|[208 — MessageInspectorAfterReceiveInvoked](208-messageinspectorafterreceiveinvoked.md)|Сведения|Диспетчер вызвал AfterReceiveReply относительно MessageInspector типа «%1».|Troubleshooting, ServiceModel|  
|[209 — MessageInspectorBeforeSendInvoked](209-messageinspectorbeforesendinvoked.md)|Сведения|Диспетчер вызвал BeforeSendRequest для MessageInspector типа «%1».|Troubleshooting, ServiceModel|  
|[210 — MessageThrottleExceeded](210-messagethrottleexceeded.md)|Предупреждение|Был достигнут предел ограничителя «%1» из «%2».|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[211 — ParameterInspectorAfterCallInvoked](211-parameterinspectoraftercallinvoked.md)|Сведения|Диспетчер вызвал AfterCall относительно ParameterInspector типа «%1».|Troubleshooting, ServiceModel|  
|[212 — ParameterInspectorBeforeCallInvoked](212-parameterinspectorbeforecallinvoked.md)|Сведения|Диспетчер вызвал BeforeCall для ParameterInspector типа «%1».|Troubleshooting, ServiceModel|  
|[213 — ServiceHostStarted](213-servicehoststarted.md)|LogAlways|ServiceHost запущена: «%1».|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[214 — OperationCompleted](214-operationcompleted.md)|Сведения|OperationInvoker завершил вызов метода «%1».  Длительность вызова метода составила «%2» мс.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[215 — MessageReceivedByTransport](215-messagereceivedbytransport.md)|Сведения|Диспетчер получил сообщение от «%1».|Troubleshooting, ServiceModel|  
|[216 — MessageSentByTransport](216-messagesentbytransport.md)|Сведения|Транспорт отправил сообщение «%1».|Troubleshooting, ServiceModel|  
|[217 — ClientOperationPrepared](217-clientoperationprepared.md)|Сведения|Клиент выполняет операцию «%1», определенную в контракте «%2». Сообщение будет отправлено «%3».|Troubleshooting, ServiceModel|  
|[218 — ClientOperationCompleted](218-clientoperationcompleted.md)|Сведения|Клиент завершил выполнение операции «%1», определенной в контракте «%2». Сообщение было отправлено «%3».|Troubleshooting, ServiceModel|  
|[219 — ServiceException](219-serviceexception.md)|Ошибка|Во время обработки сообщения возникло необработанное исключение типа «%2».  Полное исключение ToString: %1.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[220 — MessageSentToTransport](220-messagesenttotransport.md)|Сведения|Диспетчер отправил сообщение транспорту. Идентификатор корреляции == «%1».|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[221 — MessageReceivedFromTransport](221-messagereceivedfromtransport.md)|Сведения|Диспетчер получил сообщение от транспорта. Идентификатор корреляции == «%1».|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[222 — OperationFailed](222-operationfailed.md)|Предупреждение|Метод «%1» вызвал необработанное исключение после того, как был вызван OperationInvoker. Длительность вызова метода составила «%2» мс.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[223 — OperationFaulted](223-operationfaulted.md)|Предупреждение|Метод «%1» вызывал исключение FaultException после того, как был вызван OperationInvoker. Длительность вызова метода составила «%2» мс.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[224 — MessageThrottleAtSeventyPercent](224-messagethrottleatseventypercent.md)|Предупреждение|Предел регулировщика «%1» из «%2» находится на отметке 70 %.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[226 — IdleServicesClosed](226-idleservicesclosed.md)|LogAlways|Закрыто %1 простаивающих служб из %2 активированных служб.|HealthMonitoring WebHost|  
|[301 — UserDefinedErrorOccurred](301-userdefinederroroccurred.md)|Ошибка|Имя: «%1», ссылка: «%2», полезные данные: %3.|UserEvents, HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[302 — UserDefinedWarningOccurred](302-userdefinedwarningoccurred.md)|Предупреждение|Имя: «%1», ссылка: «%2», полезные данные: %3.|UserEvents, HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[303 — UserDefinedInformationEventOccured](303-userdefinedinformationeventoccured.md)|Сведения|Имя: «%1», ссылка: «%2», полезные данные: %3.|UserEvents, HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[401 — StopSignPostEvent](401-stopsignpostevent.md)|Сведения|Граница действия.|Устранение неполадок|  
|[402 — StartSignpostEvent](402-startsignpostevent.md)|Сведения|Граница действия.|Устранение неполадок|  
|[403 — SuspendSignpostEvent](403-suspendsignpostevent.md)|Сведения|Граница действия.|Устранение неполадок|  
|[404 — ResumeSignpostEvent](404-resumesignpostevent.md)|Сведения|Граница действия.|Устранение неполадок|  
|[451 — MessageLogInfo](451-messageloginfo.md)|Сведения|%1|Troubleshooting, WCFMessageLogging|  
|[452 — MessageLogWarning](452-messagelogwarning.md)|Предупреждение|%1|Troubleshooting, WCFMessageLogging|  
|[499 — TransferEmitted](499-transferemitted.md)|LogAlways|Произошло событие передачи.|Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging|  
|[501 — CompilationStart](501-compilationstart.md)|Сведения|Начало компиляции.|WebHost|  
|[502 — CompilationStop](502-compilationstop.md)|Сведения|Конец компиляции.|WebHost|  
|[503 — ServiceHostFactoryCreationStart](503-servicehostfactorycreationstart.md)|Сведения|Начало создания ServiceHostFactory.|WebHost|  
|[504 — ServiceHostFactoryCreationStop](504-servicehostfactorycreationstop.md)|Сведения|Окончание создания ServiceHostFactory.|WebHost|  
|[505 — CreateServiceHostStart](505-createservicehoststart.md)|Сведения|Начало CreateServiceHost.|WebHost|  
|[506 — CreateServiceHostStop](506-createservicehoststop.md)|Сведения|Конец CreateServiceHost.|WebHost|  
|[507 — HostedTransportConfigurationManagerConfigInitStart](507-hostedtransportconfigurationmanagerconfiginitstart.md)|Сведения|Запуск инициализации конфигурации HostedTransportConfigurationManager.|WebHost|  
|[508 — HostedTransportConfigurationManagerConfigInitStop](508-hostedtransportconfigurationmanagerconfiginitstop.md)|Сведения|Инициализация окончания конфигурации HostedTransportConfigurationManager.|WebHost|  
|[509 — ServiceHostOpenStart](509-servicehostopenstart.md)|Сведения|Инициализация окончания конфигурации HostedTransportConfigurationManager.|ServiceHost|  
|[510 — ServiceHostOpenStop](510-servicehostopenstop.md)|Сведения|Метод ServiceHost Open завершен.|ServiceHost|  
|[513 — WebHostRequestStart](513-webhostrequeststart.md)|Сведения|Получен запрос с виртуальным путем «%2» от AppDomain «%1».|WebHost|  
|[514 — WebHostRequestStop](514-webhostrequeststop.md)|Сведения|Остановка WebHostRequest.|WebHost|  
|[601 — CBAEntryRead](601-cbaentryread.md)|Verbose|Обработанный относительный адрес элемента ServiceActivation: «%1»; нормализованный относительный адрес: «%2».||  
|[602 — CBAMatchFound](602-cbamatchfound.md)|Verbose|Входящий запрос соответствует элементу ServiceActivation с адресом «%1».||  
|[603 — AspNetRoutingService](603-aspnetroutingservice.md)|Verbose|Входящий запрос соответствует службе WCF, заданной в маршруте Asp.Net, с адресом %1.|Службы маршрутизации|  
|[604 — AspNetRoute](604-aspnetroute.md)|Verbose|Добавлен новый маршрут Asp.Net «%1» с типом службы «%2» и типом serviceHostFactoryType «%3».|Службы маршрутизации|  
|[605 — IncrementBusyCount](605-incrementbusycount.md)|Verbose|Вызван метод IncrementBusyCount. Источник: %1|WebHost|  
|[606 — DecrementBusyCount](606-decrementbusycount.md)|Verbose|Вызван метод DecrementBusyCount. Источник: %1|WebHost|  
|[701 — ServiceChannelOpenStart](701-servicechannelopenstart.md)|Verbose|ServiceChannelOpen запущен.|WebHost|  
|[702 — ServiceChannelOpenStop](702-servicechannelopenstop.md)|Сведения|ServiceChannelOpen завершен.|ServiceModel|  
|[703 — ServiceChannelCallStart](703-servicechannelcallstart.md)|Сведения|Запущен ServiceChannelCall.|ServiceModel|  
|[704 — ServiceChannelBeginCallStart](704-servicechannelbegincallstart.md)|Сведения|Запущены асинхронные вызовы ServiceChannel.|ServiceModel|  
|[706 — HttpSendMessageStart](706-httpsendmessagestart.md)|Verbose|Запуск запроса на отправку HTTP.|HTTP|  
|[707 — HttpSendStop](707-httpsendstop.md)|Verbose|Остановка запроса на отправку HTTP.|HTTP|  
|[708 — HttpMessageReceiveStart](708-httpmessagereceivestart.md)|Verbose|Сообщение, полученное от транспорта HTTP.|HTTP|  
|[709 — DispatchMessageStart](709-dispatchmessagestart.md)|Сведения|Диспетчеризация сообщений запущена.|ServiceModel|  
|[710 — HttpContextBeforeProcessAuthentication](710-httpcontextbeforeprocessauthentication.md)|Verbose|Запустить проверку подлинности для диспетчеризации сообщений.|ServiceModel|  
|[711 — DispatchMessageBeforeAuthorization](711-dispatchmessagebeforeauthorization.md)|Verbose|Запустить авторизацию для диспетчеризации сообщений.|ServiceModel|  
|[712 — DispatchMessageStop](712-dispatchmessagestop.md)|Сведения|Диспетчеризация сообщений завершена.|ServiceModel|  
|[715 — ClientChannelOpenStart](715-clientchannelopenstart.md)|Сведения|Начало открытия ServiceChannel.|ServiceModel|  
|[716 — ClientChannelOpenStop](716-clientchannelopenstop.md)|Сведения|Остановка открытия ServiceChannel.|ServiceModel|  
|[717 — HttpSendStreamedMessageStart](717-httpsendstreamedmessagestart.md)|Сведения|Запущено потоковое сообщение об отправке HTTP.|HTTP|  
|[1400 — ChannelInitializationTimeout](1400-channelinitializationtimeout.md)|Ошибка|1 %|ServiceModel|  
|[1401 — CloseTimeout](1401-closetimeout.md)|Ошибка|1 %|ServiceModel|  
|[1402 — IdleTimeout](1402-idletimeout.md)|Ошибка|Ключ пула соединений %1: %2|ServiceModel|  
|[1403 — LeaseTimeout](1403-leasetimeout.md)|Сведения|Ключ пула соединений %1: %2|ServiceModel|  
|[1405 — OpenTimeout](1405-opentimeout.md)|Ошибка|%1|ServiceModel|  
|[1406 — ReceiveTimeout](1406-receivetimeout.md)|Ошибка|%1|ServiceModel|  
|[1407 — SendTimeout](1407-sendtimeout.md)|Ошибка|%1|ServiceModel|  
|[1409 — InactivityTimeout](1409-inactivitytimeout.md)|Сведения|%1|ServiceModel|  
|[1416 — MaxReceivedMessageSizeExceeded](1416-maxreceivedmessagesizeexceeded.md)|Ошибка|%1|Квота|  
|[1417 — MaxSentMessageSizeExceeded](1417-maxsentmessagesizeexceeded.md)|Ошибка|%1|Квота|  
|[1418 — MaxOutboundConnectionsPerEndpointExceeded](1418-maxoutboundconnectionsperendpointexceeded.md)|Сведения|%1|Квота|  
|[1419 — MaxPendingConnectionsExceeded](1419-maxpendingconnectionsexceeded.md)|Сведения|%1|Квота|  
|[1420 — ReaderQuotaExceeded](1420-readerquotaexceeded.md)|Ошибка|%1|Квота|  
|[1422 — NegotiateTokenAuthenticatorStateCacheExceeded](1422-negotiatetokenauthenticatorstatecacheexceeded.md)|Ошибка|%1|Квота|  
|[1423 — NegotiateTokenAuthenticatorStateCacheRatio](1423-negotiatetokenauthenticatorstatecacheratio.md)|Verbose|Отношение кэша состояния структуры проверки подлинности токена согласования: %1/%2|Квота|  
|[1424 — SecuritySessionRatio](1424-securitysessionratio.md)|Verbose|Отношение сеанса безопасности: %1/%2|Квота|  
|[1430 — PendingConnectionsRatio](1430-pendingconnectionsratio.md)|Verbose|Отношение ожидающих соединений: %1/%2|Квота|  
|[1431 — ConcurrentCallsRatio](1431-concurrentcallsratio.md)|Verbose|Отношение одновременных сеансов: %1/%2|Квота|  
|[1432 — ConcurrentSessionsRatio](1432-concurrentsessionsratio.md)|Verbose|Отношение одновременных сеансов: %1/%2|Квота|  
|[1433 — OutboundConnectionsPerEndpointRatio](1433-outboundconnectionsperendpointratio.md)|Verbose|Отношение исходящих соединений на конечную точку: %1/%2|Квота|  
|[1436 — PendingMessagesPerChannelRatio](1436-pendingmessagesperchannelratio.md)|Verbose|Отношение ожидающих сообщений на канал: %1/%2|Квота|  
|[1438 — ConcurrentInstancesRatio](1438-concurrentinstancesratio.md)|Verbose|Отношение одновременных экземпляров: %1/%2|Квота|  
|[1439 — PendingAcceptsAtZero](1439-pendingacceptsatzero.md)|Сведения|Ожидающих принятий не осталось|Квота|  
|[1441 — MaxSessionSizeReached](1441-maxsessionsizereached.md)|Предупреждение|1 %|Квота|  
|[1442 — ReceiveRetryCountReached](1442-receiveretrycountreached.md)|Предупреждение|Число повторных попыток достигнуто для сообщения MSMQ с идентификатором «%1»|Квота|  
|[1443 — MaxRetryCyclesExceededMsmq](1443-maxretrycyclesexceededmsmq.md)|Ошибка|Максимальное число циклов повтора превышено для сообщения MSMQ с идентификатором «%1»|Квота|  
|[1445 — ReadPoolMiss](1445-readpoolmiss.md)|Verbose|Создан новый объект «%1»|Квота|  
|[1446 — WritePoolMiss](1446-writepoolmiss.md)|Verbose|Создан новый объект «%1»|Квота|  
|[1451 — MaxRetryCyclesExceeded](1451-maxretrycyclesexceeded.md)|Ошибка|1 %|Квота|  
|[3300 — ReceiveContextCompleteFailed](3300-receivecontextcompletefailed.md)|Предупреждение|Не удалось завершить %1.|Канал|  
|[3301 — ReceiveContextAbandonFailed](3301-receivecontextabandonfailed.md)|Предупреждение|Не удалось отменить %1.|Канал|  
|[3303 — ReceiveContextAbandonWithException](3303-receivecontextabandonwithexception.md)|Предупреждение|Сбой получения контекста.|ServiceModel|  
|[3303 — ReceiveContextAbandonWithException](3303-receivecontextabandonwithexception.md)|Сведения|%1 был прекращен с исключением %2.|Канал|  
|[3305 — ClientBaseCachedChannelFactoryCount](3305-clientbasecachedchannelfactorycount.md)|Сведения|Число кэшированных фабрик каналов: «%1».  Максимальное число фабрик каналов для кэширования:  «%2».|ServiceModel|  
|[3306 — ClientBaseChannelFactoryAgedOutofCache](3306-clientbasechannelfactoryagedoutofcache.md)|Сведения|Фабрика канала устарела и была удалена из кэша, так как объем кэша достиг предела «%1».|ServiceModel|  
|[3307 — ClientBaseChannelFactoryCacheHit](3307-clientbasechannelfactorycachehit.md)|Сведения|В кэше обнаружена использованная одинаковая фабрика каналов.|ServiceModel|  
|[3308 — ClientBaseUsingLocalChannelFactory](3308-clientbaseusinglocalchannelfactory.md)|Сведения|Фабрика каналов из кэша не используется, т. е. кэширование отключено для экземпляра.|ServiceModel|  
|[3309 — QueryCompositionExecuted](3309-querycompositionexecuted.md)|Сведения|Построение запроса с помощью «%1» было выполнено для URI запроса: «%2».|ServiceModel|  
|[3310 — DispatchFailed](3310-dispatchfailed.md)|Ошибка|Операция «%1» была подготовлена с ошибками.|ServiceModel|  
|[3311 — DispatchSuccessful](3311-dispatchsuccessful.md)|Сведения|Операция «%1» была успешно подготовлена.|ServiceModel|  
|[3312 — MessageReadByEncoder](3312-messagereadbyencoder.md)|Сведения|Сообщение размером «%1» байт прочитано кодировщиком.|Канал|  
|[3312 — MessageReadByEncoder](3312-messagereadbyencoder.md)|Сведения|Сообщение размером «%1» байт записано кодировщиком.|Канал|  
|[3314 — SessionIdleTimeout](3314-sessionidletimeout.md)|Ошибка|Прерывание сеанса для простаивающего канала по URI: «%1».|ServiceModel|  
|[3319 — SocketAcceptEnqueued](3319-socketacceptenqueued.md)|Verbose|Запущено принятие соединения.|TCP|  
|[3320 — SocketAccepted](3320-socketaccepted.md)|Verbose|ListenerId:%1 принял SocketId:%2.|TCP|  
|[3321 — ConnectionPoolMiss](3321-connectionpoolmiss.md)|Verbose|В пуле для %1 нет доступного соединения и есть %2 занятых соединений.|Канал|  
|[3322 — DispatchFormatterDeserializeRequestStart](3322-dispatchformatterdeserializerequeststart.md)|Verbose|Диспетчер начал десериализацию сообщения запроса.|ServiceModel|  
|[3323 — DispatchFormatterDeserializeRequestStop](3323-dispatchformatterdeserializerequeststop.md)|Verbose|Диспетчер завершил десериализацию сообщения запроса.|ServiceModel|  
|[3324 — DispatchFormatterSerializeReplyStart](3324-dispatchformatterserializereplystart.md)|Verbose|Диспетчер начал сериализацию ответного сообщения.|ServiceModel|  
|[3325 — DispatchFormatterSerializeReplyStop](3325-dispatchformatterserializereplystop.md)|Verbose|Диспетчер завершил сериализацию ответного сообщения.|ServiceModel|  
|[3326 — ClientFormatterSerializeRequestStart](3326-clientformatterserializerequeststart.md)|Verbose|Клиент начал сериализацию запроса.|ServiceModel|  
|[3327 — ClientFormatterSerializeRequestStop](3327-clientformatterserializerequeststop.md)|Verbose|Клиент завершил сериализацию сообщения запроса.|ServiceModel|  
|[3328 — ClientFormatterDeserializeReplyStart](3328-clientformatterdeserializereplystart.md)|Verbose|Клиент начал десериализацию ответного сообщения.|ServiceModel|  
|[3329 — ClientFormatterDeserializeReplyStop](3329-clientformatterdeserializereplystop.md)|Verbose|Клиент завершил десериализацию ответного сообщения.|ServiceModel|  
|[3330 — SecurityNegotiationStart](3330-securitynegotiationstart.md)|Verbose|Начато согласование безопасности.|Безопасность|  
|[3331 — SecurityNegotiationStop](3331-securitynegotiationstop.md)|Verbose|Согласование безопасности завершено.|Безопасность|  
|[3332 — SecurityTokenProviderOpened](3332-securitytokenprovideropened.md)|Verbose|Открытие SecurityTokenProvider завершено.|Безопасность|  
|[3333 — OutgoingMessageSecured](3333-outgoingmessagesecured.md)|Verbose|Исходящее сообщение защищено.|Безопасность|  
|[3334 — IncomingMessageVerified](3334-incomingmessageverified.md)|Verbose|Входящее сообщение проверено.|Безопасность ServiceModel|  
|[3335 — GetServiceInstanceStart](3335-getserviceinstancestart.md)|Verbose|Начато получение экземпляра службы.|ServiceModel|  
|[3336 — GetServiceInstanceStop](3336-getserviceinstancestop.md)|Verbose|Экземпляр службы получен.|ServiceModel|  
|[3337 — ChannelReceiveStart](3337-channelreceivestart.md)|Verbose|ChannelHandlerId:%1 - цикл получения сообщений запущен.|Канал|  
|[3338 — ChannelReceiveStop](3338-channelreceivestop.md)|Verbose|ChannelHandlerId:%1 - цикл получения сообщений остановлен.|Канал|  
|[3339 — ChannelFactoryCreated](3339-channelfactorycreated.md)|Verbose|ChannelFactory создана.|ServiceModel|  
|[3340 — PipeConnectionAcceptStart](3340-pipeconnectionacceptstart.md)|Verbose|Запущено принятие соединение по каналу %1.|Канал|  
|[3341 — PipeConnectionAcceptStop](3341-pipeconnectionacceptstop.md)|Verbose|Соединение по каналу принято.|Канал|  
|[3342 — EstablishConnectionStart](3342-establishconnectionstart.md)|Verbose|Установление соединения для %1 запущено.|Канал|  
|[3343 — EstablishConnectionStop](3343-establishconnectionstop.md)|Verbose|Соединение установлено.|Канал|  
|[3345 — SessionPreambleUnderstood](3345-sessionpreambleunderstood.md)|Verbose|Начальная часть сеанса для «%1» распознана.|Канал|  
|[3346 — ConnectionReaderSendFault](3346-connectionreadersendfault.md)|Ошибка|Ошибка при отправке модуля чтения соединения «%1».|Канал|  
|[3347 — SocketAcceptClosed](3347-socketacceptclosed.md)|Verbose|Принятие сокета закрыто.|TCP|  
|[3348 — ServiceHostFaulted](3348-servicehostfaulted.md)|Critical|Сбой узла службы.|TCP|  
|[3349 — ListenerOpenStart](3349-listeneropenstart.md)|Verbose|Открытие прослушивателя для «%1».|Канал|  
|[3350 — ListenerOpenStop](3350-listeneropenstop.md)|Verbose|Открытие прослушивателя завершено.|Канал|  
|[3351 — ServerMaxPooledConnectionsQuotaReached](3351-servermaxpooledconnectionsquotareached.md)|Verbose|Достигнута квота максимального числа соединений в пуле.|Квота|  
|[3352 — TcpConnectionTimedOut](3352-tcpconnectiontimedout.md)|Ошибка|Истекло время ожидания SocketId:%1 с удаленным адресом %2.|TCP|  
|[3353 — TcpConnectionResetError](3353-tcpconnectionreseterror.md)|Предупреждение|Ошибка сброса соединения SocketId:%1 с удаленным адресом %2.|TCP|  
|[3354 — ServiceSecurityNegotiationCompleted](3354-servicesecuritynegotiationcompleted.md)|Verbose|Согласование безопасности службы завершено.|Безопасность|  
|[3355 — SecurityNegotiationProcessingFailure](3355-securitynegotiationprocessingfailure.md)|Ошибка|Сбой обработки согласования безопасности.|Безопасность|  
|[3356 — SecurityIdentityVerificationSuccess](3356-securityidentityverificationsuccess.md)|Verbose|Проверка безопасности выполнена успешно.|Безопасность|  
|[3357 — SecurityIdentityVerificationFailure](3357-securityidentityverificationfailure.md)|Ошибка|Ошибка при проверке безопасности.|Безопасность|  
|[3358 — PortSharingDuplicatedSocket](3358-portsharingduplicatedsocket.md)|Verbose|Сокет дублирован для %1.|Службы активации|  
|[3359 — SecurityImpersonationSuccess](3359-securityimpersonationsuccess.md)|Verbose|Олицетворение безопасности успешно выполнено.|Безопасность|  
|[3360 — SecurityImpersonationFailure](3360-securityimpersonationfailure.md)|Предупреждение|Сбой олицетворения безопасности.|Безопасность|  
|[3361 — HttpChannelRequestAborted](3361-httpchannelrequestaborted.md)|Предупреждение|Запрос канала HTTP прерван.|HTTP|  
|[3362 — HttpChannelResponseAborted](3362-httpchannelresponseaborted.md)|Предупреждение|Ответ на запрос канала HTTP прерван.|HTTP|  
|[3363 — HttpAuthFailed](3363-httpauthfailed.md)|Предупреждение|Ошибка аутентификации HTTP.|HTTP|  
|[3364 — SharedListenerProxyRegisterStart](3364-sharedlistenerproxyregisterstart.md)|Verbose|Начата регистрация SharedListenerProxy для URI «%1».|Службы активации|  
|[3365 — SharedListenerProxyRegisterStop](3365-sharedlistenerproxyregisterstop.md)|Verbose|Остановка регистрации SharedListenerProxy.|Службы активации|  
|[3366 — SharedListenerProxyRegisterFailed](3366-sharedlistenerproxyregisterfailed.md)|Ошибка|Не удалось выполнить регистрацию SharedListenerProxy с состоянием «%1».|Службы активации|  
|[3367 — ConnectionPoolPreambleFailed](3367-connectionpoolpreamblefailed.md)|Ошибка|ConnectionPoolPreambleFailed.|Канал|  
|[3368 — SslOnInitiateUpgrade](3368-ssloninitiateupgrade.md)|Verbose|SslOnAcceptUpgradeStart|Безопасность|  
|[3369 — SslOnAcceptUpgrade](3369-sslonacceptupgrade.md)|Verbose|SslOnAcceptUpgradeStop|Безопасность|  
|[3370 — BinaryMessageEncodingStart](3370-binarymessageencodingstart.md)|Verbose|BinaryMessageEncoder начал кодирование сообщения.|Канал|  
|[3371 — MtomMessageEncodingStart](3371-mtommessageencodingstart.md)|Verbose|MtomMessageEncoder начал кодирование сообщения.|Канал|  
|[3372 — TextMessageEncodingStart](3372-textmessageencodingstart.md)|Verbose|TextMessageEncoder начал кодирование сообщения.|Канал|  
|[3373 — BinaryMessageDecodingStart](3373-binarymessagedecodingstart.md)|Verbose|BinaryMessageEncoder начал расшифровку сообщения.|Канал|  
|[3374 — MtomMessageDecodingStart](3374-mtommessagedecodingstart.md)|Verbose|Mtommessageencoder начал начата декодирование сообщения.|Канал|  
|[3375 — TextMessageDecodingStart](3375-textmessagedecodingstart.md)|Verbose|TextMessageEncoder начал расшифровку сообщения.|Канал|  
|[3376 — HttpResponseReceiveStart](3376-httpresponsereceivestart.md)|Сведения|Транспорт HTTP начал получение сообщения.|HTTP|  
|[3377 — SocketReadStop](3377-socketreadstop.md)|Verbose|SocketId: %1 прочел «%2» байт по адресу «%3».|TCP|  
|[3378 — SocketAsyncReadStop](3378-socketasyncreadstop.md)|Verbose|SocketId: %1 прочел «%2» байт по адресу «%3».|TCP|  
|[3379 — SocketWriteStart](3379-socketwritestart.md)|Verbose|SocketId: %1 записывает «%2» байт по адресу «%3».|TCP|  
|[3380 — SocketAsyncWriteStart](3380-socketasyncwritestart.md)|Verbose|SocketId: %1 записывает «%2» байт по адресу «%3».|TCP|  
|[3381 — SequenceAcknowledgementSent](3381-sequenceacknowledgementsent.md)|Verbose|Подтверждение SessionId: %1 отправлено.|Канал|  
|[3382 — ClientReliableSessionReconnect](3382-clientreliablesessionreconnect.md)|Сведения|Повторное подключение SessionId:%1.|Канал|  
|[3383 — ReliableSessionChannelFaulted](3383-reliablesessionchannelfaulted.md)|Сведения|Сбой SessionId:%1.|Канал|  
|[3384 — WindowsStreamSecurityOnInitiateUpgrade](3384-windowsstreamsecurityoninitiateupgrade.md)|Verbose|WindowsStreamSecurity инициирует обновление безопасности.|Безопасность|  
|[3385 — WindowsStreamSecurityOnAcceptUpgrade](3385-windowsstreamsecurityonacceptupgrade.md)|Verbose|Потоковая безопасность Windows для обновления принятия.|Безопасность|  
|[3386 — SocketConnectionAbort](3386-socketconnectionabort.md)|Предупреждение|Прерывание SocketId:%1.|TCP|  
|[3388 — HttpGetContextStart](3388-httpgetcontextstart.md)|Verbose|Начало HttpGetContext.|HTTP|  
|[3389 — ClientSendPreambleStart](3389-clientsendpreamblestart.md)|Verbose|Запуск отправки клиентом начальной части.|Канал|  
|[3390 — ClientSendPreambleStop](3390-clientsendpreamblestop.md)|Verbose|Остановка отправки клиентом начальной части.|Канал|  
|[3391 — HttpMessageReceiveFailed](3391-httpmessagereceivefailed.md)|Предупреждение|Ошибка при получении сообщения HTTP.|HTTP|  
|[3392 — TransactionScopeCreate](3392-transactionscopecreate.md)|Сведения|TransactionScope создается с LocalIdentifier:«%1» и DistributedIdentifier:«%2».|ServiceModel|  
|[3393 — StreamedMessageReadByEncoder](3393-streamedmessagereadbyencoder.md)|Сведения|Потоковое сообщение было прочитано кодировщиком.|Канал|  
|[3394 — StreamedMessageWrittenByEncoder](3394-streamedmessagewrittenbyencoder.md)|Сведения|Потоковое сообщение было записано кодировщиком.|Канал|  
|[3395 — MessageWrittenAsynchronouslyByEncoder](3395-messagewrittenasynchronouslybyencoder.md)|Сведения|Сообщение было записано кодировщиком в асинхронном режиме.|Канал|  
|[3396 — BufferedAsyncWriteStart](3396-bufferedasyncwritestart.md)|Сведения|BufferId:%1 завершена запись «%2» байт в базовый поток.|Канал|  
|[3397 — BufferedAsyncWriteStop](3397-bufferedasyncwritestop.md)|Сведения|Сообщение было записано кодировщиком в асинхронном режиме.|Канал|  
|[3398 — PipeSharedMemoryCreated](3398-pipesharedmemorycreated.md)|Verbose|Общая память канала создана в «%1».|Канал|  
|[3399 — NamedPipeCreated](3399-namedpipecreated.md)|Verbose|NamedPipe-канал «%1» создан.|Канал|  
|[3401 — SignatureVerificationStart](3401-signatureverificationstart.md)|Verbose|Начата проверка сигнатуры.|Безопасность|  
|[3402 — SignatureVerificationSuccess](3402-signatureverificationsuccess.md)|Verbose|Проверка сигнатуры успешно завершена.|Безопасность|  
|[3403 — WrappedKeyDecryptionStart](3403-wrappedkeydecryptionstart.md)|Verbose|Расшифровка упакованного ключа запущена.|Безопасность|  
|[3404 — WrappedKeyDecryptionSuccess](3404-wrappedkeydecryptionsuccess.md)|Verbose|Расшифровка упакованного ключа выполнена успешно.|Безопасность|  
|[3405 — EncryptedDataProcessingStart](3405-encrypteddataprocessingstart.md)|Verbose|Обработка зашифрованных данных запущена.|Безопасность|  
|[3406 — EncryptedDataProcessingSuccess](3406-encrypteddataprocessingsuccess.md)|Verbose|Шифрование данных выполнено успешно.|Безопасность|  
|[3407 — HttpPipelineProcessInboundRequestStart](3407-httppipelineprocessinboundrequeststart.md)|Verbose|Обработчик сообщений HTTP начал обработку входящего запроса.|HTTP|  
|[3408 — HttpPipelineBeginProcessInboundRequestStart](3408-httppipelinebeginprocessinboundrequeststart.md)|Verbose|Обработчик сообщений HTTP начал асинхронную обработку входящего запроса.|HTTP|  
|[3409 — HttpPipelineProcessInboundRequestStop](3409-httppipelineprocessinboundrequeststop.md)|Verbose|Обработчик сообщений HTTP завершил обработку входящего запроса.|HTTP|  
|[3410 — HttpPipelineFaulted](3410-httppipelinefaulted.md)|Предупреждение|Работа обработчика сообщений HTTP завершилась ошибкой.|HTTP|  
|[3411 — HttpPipelineTimeoutException](3411-httppipelinetimeoutexception.md)|Ошибка|Истекло время ожидания соединения WebSocket.|HTTP|  
|[3412 — HttpPipelineProcessResponseStart](3412-httppipelineprocessresponsestart.md)|Verbose|Обработчик сообщений HTTP начал обработку запроса.|HTTP|  
|[3413 — HttpPipelineBeginProcessResponseStart](3413-httppipelinebeginprocessresponsestart.md)|Verbose|Обработчик сообщений HTTP начал асинхронную обработку запроса.|HTTP|  
|[3414 — HttpPipelineProcessResponseStop](3414-httppipelineprocessresponsestop.md)|Verbose|Обработчик сообщений HTTP завершил обработку запроса.|HTTP|  
|[3415 — WebSocketConnectionRequestSendStart](3415-websocketconnectionrequestsendstart.md)|Verbose|Запрос соединения WebSocket к «%1» отправляет сигнал к началу.|HTTP|  
|[3416 — WebSocketConnectionRequestSendStop](3416-websocketconnectionrequestsendstop.md)|Verbose|Запрос на соединение WebSocketId:%1 отправлен.|HTTP|  
|[3417 — WebSocketConnectionAcceptStart](3417-websocketconnectionacceptstart.md)|Verbose|Начато соединение WebSocket.|HTTP|  
|[3418 — WebSocketConnectionAccepted](3418-websocketconnectionaccepted.md)|Verbose|WebSocketId: запрос на соединение с %1 принят.|HTTP|  
|[3419 — WebSocketConnectionDeclined](3419-websocketconnectiondeclined.md)|Ошибка|Соединение WebSocket отклонено с кодом состояния «%1»|HTTP|  
|[3420 — WebSocketConnectionFailed](3420-websocketconnectionfailed.md)|Ошибка|Запрос на обновление WebSocket завершился с ошибкой: «%1»|HTTP|  
|[3421 — WebSocketConnectionAborted](3421-websocketconnectionaborted.md)|Ошибка|WebSocketId:%1 - соединение прервано.|HTTP|  
|[3422 — WebSocketAsyncWriteStart](3422-websocketasyncwritestart.md)|Verbose|WebSocketId:%1 - запись «%2» байт по адресу «%3».|HTTP|  
|[3423 — WebSocketAsyncWriteStop](3423-websocketasyncwritestop.md)|Verbose|Асинхронная запись WebSocketId:%1 остановлена.|HTTP|  
|[3424 — WebSocketAsyncReadStart](3424-websocketasyncreadstart.md)|Verbose|WebSocketId: начало чтения для %1.|HTTP|  
|[3425 — WebSocketAsyncReadStop](3425-websocketasyncreadstop.md)|Verbose|WebSocketId: %1 читает «%2» байт по адресу «%3».|HTTP|  
|[3426 — WebSocketCloseSent](3426-websocketclosesent.md)|Verbose|WebSocketId:%1 - отправка сообщения о закрытии по адресу «%2» с состоянием закрытия «%3».|HTTP|  
|[3427 — WebSocketCloseOutputSent](3427-websocketcloseoutputsent.md)|Verbose|WebSocketId: %1 - отправка выходного сообщения о закрытии по адресу «%2» с состоянием закрытия «%3».|HTTP|  
|[3428 — WebSocketConnectionClosed](3428-websocketconnectionclosed.md)|Verbose|Соединение WebSocketId:%1 закрыто.|HTTP|  
|[3429 — WebSocketCloseStatusReceived](3429-websocketclosestatusreceived.md)|Verbose|Получено сообщение о закрытии соединения WebSocketId:%1 с состоянием «%2».|HTTP|  
|[3430 — WebSocketUseVersionFromClientWebSocketFactory](3430-websocketuseversionfromclientwebsocketfactory.md)|Verbose|Используется версия WebSocketVersion из фабрики клиентского соединения WebSocket типа «%1».|HTTP|  
|[3431 — WebSocketCreateClientWebSocketWithFactory](3431-websocketcreateclientwebsocketwithfactory.md)|Verbose|Создание клиентского соединения WebSocket с фабрикой типа «%1».|HTTP|  
|[3553 — XamlServicesLoadStart](3553-xamlservicesloadstart.md)|Сведения|Запуск XamlServicesLoad|WebHost|  
|[3554 — XamlServicesLoadStop](3554-xamlservicesloadstop.md)|Сведения|Остановка XamlServicesLoad|WebHost|  
|[3555 — CreateWorkflowServiceHostStart](3555-createworkflowservicehoststart.md)|Сведения|Запуск CreateWorkflowServiceHost|WebHost|  
|[3556 — CreateWorkflowServiceHostStop](3556-createworkflowservicehoststop.md)|Сведения|Остановка CreateWorkflowServiceHost|WebHost|  
|[3558 — ServiceActivationStart](3558-serviceactivationstart.md)|Сведения|Запуск активации службы|WebHost|  
|[3559 — ServiceActivationStop](3559-serviceactivationstop.md)|Сведения|Остановка активации службы|WebHost|  
|[3560 — ServiceActivationAvailableMemory](3560-serviceactivationavailablememory.md)|Verbose|Объем доступной памяти (в байтах): %1|Квота|  
|[3800 — RoutingServiceClosingClient](3800-routingserviceclosingclient.md)|Сведения|Служба маршрутизации закрывает клиент «%1».|Службы маршрутизации|  
|[3800 — RoutingServiceClosingClient](3800-routingserviceclosingclient.md)|Предупреждение|Клиент службы маршрутизации «%1» завершил выполнение с ошибкой.|Службы маршрутизации|  
|[3802 — RoutingServiceCompletingOneWay](3802-routingservicecompletingoneway.md)|Сведения|Однонаправленное сообщение службы Routing Service завершается.|Службы маршрутизации|  
|[3803 — RoutingServiceProcessingFailure](3803-routingserviceprocessingfailure.md)|Ошибка|Служба маршрутизации завершена с ошибкой при обработке сообщения в конечной точке с адресом «%1».|Службы маршрутизации|  
|[3804 — RoutingServiceCreatingClientForEndpoint](3804-routingservicecreatingclientforendpoint.md)|Сведения|Служба маршрутизации создает клиент для конечной точки: «%1».|Службы маршрутизации|  
|[3805 — RoutingServiceDisplayConfig](3805-routingservicedisplayconfig.md)|Verbose|Служба маршрутизации настраивается с помощью RouteOnHeadersOnly: %1, SoapProcessingEnabled: %2, EnsureOrderedDispatch: %3.|Службы маршрутизации|  
|[3807 — RoutingServiceCompletingTwoWay](3807-routingservicecompletingtwoway.md)|Сведения|Ответное сообщение на запрос службы Routing Service завершается.|Службы маршрутизации|  
|[3809 — RoutingServiceMessageRoutedToEndpoints](3809-routingservicemessageroutedtoendpoints.md)|Verbose|Перенаправленное службой маршрутизации сообщение с идентификатором «%1» в списки конечных точек: %2.|Службы маршрутизации|  
|[3810 — RoutingServiceConfigurationApplied](3810-routingserviceconfigurationapplied.md)|Сведения|Новая конфигурация RoutingConfiguration применена к службе Routing Service.|Службы маршрутизации|  
|[3815 — RoutingServiceProcessingMessage](3815-routingserviceprocessingmessage.md)|Сведения|Служба маршрутизации обрабатывает сообщение с идентификатором «%1», действие «%2», URL-адрес «%3», получено в рамках транзакции %4.|Службы маршрутизации|  
|[3816 — RoutingServiceTransmittingMessage](3816-routingservicetransmittingmessage.md)|Сведения|Служба маршрутизации передает сообщение с идентификатором «%1» [операция %2] в «%3».|Службы маршрутизации|  
|[3817 — RoutingServiceCommittingTransaction](3817-routingservicecommittingtransaction.md)|Сведения|Служба маршрутизации выполняет фиксацию транзакции с идентификатором «%1».|Службы маршрутизации|  
|[3818 — RoutingServiceDuplexCallbackException](3818-routingserviceduplexcallbackexception.md)|Ошибка|Для компонента %1 службы маршрутизации возникло исключение дуплексного обратного вызова.|Службы маршрутизации|  
|[3819 — RoutingServiceMovedToBackup](3819-routingservicemovedtobackup.md)|Сведения|Сообщение службы маршрутизации с идентификатором «%1» [операция %2] перемещено в резервную конечную точку «%3».|Службы маршрутизации|  
|[3820 — RoutingServiceCreatingTransaction](3820-routingservicecreatingtransaction.md)|Сведения|Служба маршрутизации создала новую транзакцию с идентификатором «%1» для обработки сообщений.|Службы маршрутизации|  
|[3821 — RoutingServiceCloseFailed](3821-routingserviceclosefailed.md)|Предупреждение|Служба маршрутизации завершила выполнение с ошибкой при закрытии исходящего соединения клиента «%1».|Службы маршрутизации|  
|[3822 — RoutingServiceSendingResponse](3822-routingservicesendingresponse.md)|Сведения|Служба маршрутизации отправляет ответное сообщение с действием «%1».|Службы маршрутизации|  
|[3823 — RoutingServiceSendingFaultResponse](3823-routingservicesendingfaultresponse.md)|Предупреждение|Служба маршрутизации отправляет ответное сообщение об ошибке с действием «%1».|Службы маршрутизации|  
|[3824 — RoutingServiceCompletingReceiveContext](3824-routingservicecompletingreceivecontext.md)|Verbose|Служба маршрутизации вызывает ReceiveContext.Complete для сообщения с идентификатором: «%1».|Службы маршрутизации|  
|[3825 — RoutingServiceAbandoningReceiveContext](3825-routingserviceabandoningreceivecontext.md)|Предупреждение|Служба маршрутизации вызывает ReceiveContext.Abandon для сообщения с идентификатором: «%1».|Службы маршрутизации|  
|[3826 — RoutingServiceUsingExistingTransaction](3826-routingserviceusingexistingtransaction.md)|Verbose|Служба маршрутизации будет отправлять сообщения с помощью существующей транзакции «%1».|Службы маршрутизации|  
|[3827 — RoutingServiceTransmitFailed](3827-routingservicetransmitfailed.md)|Предупреждение|Служба маршрутизации завершена с ошибкой при отправке в «%1».|Службы маршрутизации|  
|[3828 — RoutingServiceFilterTableMatchStart](3828-routingservicefiltertablematchstart.md)|Сведения|Начало сопоставления MessageFilterTable в службе маршрутизации.|Службы маршрутизации|  
|[3829 — RoutingServiceFilterTableMatchStop](3829-routingservicefiltertablematchstop.md)|Сведения|Остановка сопоставления MessageFilterTable в службе маршрутизации.|Службы маршрутизации|  
|[3830 — RoutingServiceAbortingChannel](3830-routingserviceabortingchannel.md)|Verbose|Служба маршрутизации запрашивает прерывание по каналу «%1».|Службы маршрутизации|  
|[3831 — RoutingServiceHandledException](3831-routingservicehandledexception.md)|Verbose|Служба маршрутизации обработала исключение.|Службы маршрутизации|  
|[3832 — RoutingServiceTransmitSucceeded](3832-routingservicetransmitsucceeded.md)|Сведения|Служба маршрутизации успешно передала сообщение с идентификатором: «%1 [операция %2] в "%3"».|Службы маршрутизации|  
|[4001 — TransportListenerSessionsReceived](4001-transportlistenersessionsreceived.md)|Verbose|Сеанс прослушивателя транспорта получен по «%1»|Службы активации|  
|[4002 — FailFastException](4002-failfastexception.md)|Critical|FailFastException.|Службы активации|  
|[4003 — ServiceStartPipeError](4003-servicestartpipeerror.md)|Ошибка|Ошибка канала запуска службы.|Службы активации|  
|[4008 — DispatchSessionStart](4008-dispatchsessionstart.md)|Verbose|Диспетчеризация сеанса запущена.|Службы активации|  
|[4008 — DispatchSessionStart](4008-dispatchsessionstart.md)|Предупреждение|Сбой диспетчеризации сеанса для «%1», так как очередь ожидающих сеансов заполнена «%2» ожидающими элементами.|Службы активации|  
|[4011 — MessageQueueRegisterStart](4011-messagequeueregisterstart.md)|Verbose|Запуск регистрации очереди сообщений.|Службы активации|  
|[4012 — MessageQueueRegisterAbort](4012-messagequeueregisterabort.md)|Ошибка|Регистрация очереди сообщений прервана с состоянием «%1» для URI: «%2».|Службы активации|  
|[4013 — MessageQueueUnregisterSucceeded](4013-messagequeueunregistersucceeded.md)|Verbose|Отмена регистрации очереди сообщений успешно выполнена для URI: «%1».|Службы активации|  
|[4014 — MessageQueueRegisterFailed](4014-messagequeueregisterfailed.md)|Ошибка|Регистрация очереди сообщений для URI: «%1» завершилась ошибкой с состоянием «%2».|Службы активации|  
|[4015 — MessageQueueRegisterCompleted](4015-messagequeueregistercompleted.md)|Сведения|Регистрация очереди сообщений для URI «%1» завершена.|Службы активации|  
|[4016 — MessageQueueDuplicatedSocketError](4016-messagequeueduplicatedsocketerror.md)|Ошибка|Очереди сообщений не удалось дублировать сокет.|Службы активации|  
|[4019 — MessageQueueDuplicatedSocketComplete](4019-messagequeueduplicatedsocketcomplete.md)|Verbose|MessageQueueDuplicatedSocketComplete|Службы активации|  
|[4020 — TcpTransportListenerListeningStart](4020-tcptransportlistenerlisteningstart.md)|Verbose|Прослушиватель транспорта TCP начинает прослушивание по URI: «%1».|Службы активации|  
|[4021 — TcpTransportListenerListeningStop](4021-tcptransportlistenerlisteningstop.md)|Verbose|Прослушивание прослушивателя транспорта TCP.|Службы активации|  
|[4022 — WebhostUnregisterProtocolFailed](4022-webhostunregisterprotocolfailed.md)|Ошибка|Код ошибки: %1|Службы активации|  
|[4023 — WasCloseAllListenerChannelInstancesCompleted](4023-wasclosealllistenerchannelinstancescompleted.md)|Сведения|Закрытие WAS всех экземпляров канала прослушивателя завершено.|Службы активации|  
|[4024 — WasCloseAllListenerChannelInstancesFailed](4024-wasclosealllistenerchannelinstancesfailed.md)|Ошибка|Код ошибки: %1|Службы активации|  
|[4025 — OpenListenerChannelInstanceFailed](4025-openlistenerchannelinstancefailed.md)|Ошибка|Код ошибки: %1|Службы активации|  
|[4026 — WasConnected](4026-wasconnected.md)|Verbose|WAS подключен.|Службы активации|  
|[4027 — WasDisconnected](4027-wasdisconnected.md)|Verbose|WAS отключен.|Службы активации|  
|[4028 — PipeTransportListenerListeningStart](4028-pipetransportlistenerlisteningstart.md)|Verbose|Начало работы прослушивателя транспорта канала по URI: %1.|Службы активации|  
|[4029 — PipeTransportListenerListeningStop](4029-pipetransportlistenerlisteningstop.md)|Verbose|Остановка работы прослушивателя транспорта канала.|Службы активации|  
|[4030 — DispatchSessionSuccess](4030-dispatchsessionsuccess.md)|Сведения|Диспетчеризация сеанса выполнена успешно.|Службы активации|  
|[4031 — DispatchSessionFailed](4031-dispatchsessionfailed.md)|Ошибка|Ошибка диспетчеризации сеанса.|Службы активации|  
|[4032 — WasConnectionTimedout](4032-wasconnectiontimedout.md)|Critical|Время ожидания соединения WAS истекло.|Службы активации|  
|[4033 — RoutingTableLookupStart](4033-routingtablelookupstart.md)|Verbose|Просмотр таблицы маршрутизации запущен.|Службы активации|  
|[4034 — RoutingTableLookupStop](4034-routingtablelookupstop.md)|Verbose|Просмотр таблицы маршрутизации завершен.|Службы активации|  
|[4035 — PendingSessionQueueRatio](4035-pendingsessionqueueratio.md)|Verbose|Отношение очереди ожидающих сеансов: %1/%2|Квота|  
|[4600 — MessageLogEventSizeExceeded](4600-messagelogeventsizeexceeded.md)|Предупреждение|Сообщение не зарегистрировано в журнале, так как оно превышает размер события трассировки событий Windows|Регистрация сообщений WCF|  
|[4801 — DiscoveryClientInClientChannelFailedToClose](4801-discoveryclientinclientchannelfailedtoclose.md)|Предупреждение|Не удалось закрыть DiscoveryClient, созданный внутри DiscoveryClientChannel. Работа клиента прервана.|Обнаружение|  
|[4802 — DiscoveryClientProtocolExceptionSuppressed](4802-discoveryclientprotocolexceptionsuppressed.md)|Сведения|Исключение ProtocolException было подавлено при закрытии DiscoveryClient. Это могло произойти из-за того, что DiscoveryService по-прежнему пытается отправить ответ для DiscoveryClient.|Обнаружение|  
|[4803 — DiscoveryClientReceivedMulticastSuppression](4803-discoveryclientreceivedmulticastsuppression.md)|Сведения|DiscoveryClient получил многоадресное сообщение подавления от DiscoveryProxy.|Обнаружение|  
|[4804 — DiscoveryMessageReceivedAfterOperationCompleted](4804-discoverymessagereceivedafteroperationcompleted.md)|Сведения|Сообщение %1 с messageId="%2" отброшено клиентом DiscoveryClient, поскольку выполнена соответствующая операция %3.|Обнаружение|  
|[4805 — DiscoveryMessageWithInvalidContent](4805-discoverymessagewithinvalidcontent.md)|Предупреждение|Сообщение %1 с messageId="%2" отброшено из-за недопустимого содержимого.|Обнаружение|  
|[4806 — DiscoveryMessageWithInvalidRelatesToOrOperationCompleted](4806-discoverymessagewithinvalidrelatestooroperationcompleted.md)|Предупреждение|Сообщение %1 с messageId="%2" и relatesTo="%3" удалено клиентом DiscoveryClient, поскольку выполнена соответствующая операция %4 или значение relatesTo является недопустимым.|Обнаружение|  
|[4807 — DiscoveryMessageWithInvalidReplyTo](4807-discoverymessagewithinvalidreplyto.md)|Предупреждение|Сообщение запроса обнаружения с messageId="%1" сброшено из-за недопустимого адреса ReplyTo.|Обнаружение|  
|[4808 — DiscoveryMessageWithNoContent](4808-discoverymessagewithnocontent.md)|Предупреждение|Сообщение %1 отброшено, поскольку отсутствует его содержимое.|Обнаружение|  
|[4809 — DiscoveryMessageWithNullMessageId](4809-discoverymessagewithnullmessageid.md)|Предупреждение|Сообщение %1 удалено, поскольку заголовок сообщения не содержит обязательного свойства MessageId.|Обнаружение|  
|[4810 — DiscoveryMessageWithNullMessageSequence](4810-discoverymessagewithnullmessagesequence.md)|Предупреждение|Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку в нем отсутствует свойство DiscoveryMessageSequence.|Обнаружение|  
|[4811 — DiscoveryMessageWithNullRelatesTo](4811-discoverymessagewithnullrelatesto.md)|Предупреждение|Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку заголовок сообщения не содержит обязательного свойства RelatesTo.|Обнаружение|  
|[4812 — DiscoveryMessageWithNullReplyTo](4812-discoverymessagewithnullreplyto.md)|Предупреждение|Сообщение запроса обнаружения с messageId="%1" удалено, поскольку отсутствует адрес ReplyTo.|Обнаружение|  
|[4813 — DuplicateDiscoveryMessage](4813-duplicatediscoverymessage.md)|Предупреждение|Сообщение %1 с messageId="%2" удалено, поскольку оно является повторяющимся.|Обнаружение|  
|[4814 — EndpointDiscoverabilityDisabled](4814-endpointdiscoverabilitydisabled.md)|Сведения|Для конечной точки с EndpointAddress="%1" и ListenUri="%2" отключена возможность обнаружения.|Обнаружение|  
|[4814 — EndpointDiscoverabilityDisabled](4814-endpointdiscoverabilitydisabled.md)|Сведения|Для конечной точки с EndpointAddress="%1" и ListenUri="%2" включена возможность обнаружения.|Обнаружение|  
|[4816 — FindInitiatedInDiscoveryClientChannel](4816-findinitiatedindiscoveryclientchannel.md)|Verbose|В DiscoveryClientChannel для обнаружения конечных точек была инициирована операция поиска.|Обнаружение|  
|[4817 — InnerChannelCreationFailed](4817-innerchannelcreationfailed.md)|Предупреждение|Объекту DiscoveryClientChannel не удалось создать канал с обнаруженной конечной точкой с EndpointAddress="%1" и Via="%2". DiscoveryClientChannel попытается использовать следующую доступную из обнаруженных конечных точек.|Обнаружение|  
|[4818 — InnerChannelOpenFailed](4818-innerchannelopenfailed.md)|Предупреждение|Объекту DiscoveryClientChannel не удалось открыть канал с обнаруженной конечной точкой с EndpointAddress=«%1» и Via=«%2». DiscoveryClientChannel попытается использовать следующую доступную из обнаруженных конечных точек.|Обнаружение|  
|[4819 — InnerChannelOpenSucceeded](4819-innerchannelopensucceeded.md)|Сведения|Объект DiscoveryClientChannel успешно обнаружил конечную точку и открыл с ее помощью канал. Клиент подключен к службе с использованием EndpointAddress=«%1» и Via=«%2».|Обнаружение|  
|[4820 — SynchronizationContextReset](4820-synchronizationcontextreset.md)|Сведения|Объект DiscoveryClientChannel сбросил SynchronizationContext в исходное значение %1.|Обнаружение|  
|[4821 — SynchronizationContextSetToNull](4821-synchronizationcontextsettonull.md)|Сведения|Объект DiscoveryClientChannel установил для SynchronizationContext значение NULL перед запуском операции Find.|Обнаружение|  
|[5001 — DCSerializeWithSurrogateStart](5001-dcserializewithsurrogatestart.md)|Verbose|Запуск сериализации %1 с суррогатами, выполняемой контрактом DataContract.|Сериализация|  
|[5002 — DCSerializeWithSurrogateStop](5002-dcserializewithsurrogatestop.md)|Verbose|Остановка сериализации с суррогатами, выполняемой контрактом DataContract.|Сериализация|  
|[5003 — DCDeserializeWithSurrogateStart](5003-dcdeserializewithsurrogatestart.md)|Verbose|Запуск десериализации %1 с суррогатами, выполняемой контрактом DataContract.|Сериализация|  
|[5004 — DCDeserializeWithSurrogateStop](5004-dcdeserializewithsurrogatestop.md)|Verbose|Остановка десериализации с суррогатами, выполняемой контрактом DataContract.|Сериализация|  
|[5005 — ImportKnownTypesStart](5005-importknowntypesstart.md)|Verbose|Запуск ImportKnownTypes.|Сериализация|  
|[5006 — ImportKnownTypesStop](5006-importknowntypesstop.md)|Verbose|Остановка ImportKnownTypes.|Сериализация|  
|[5007 — DCResolverResolve](5007-dcresolverresolve.md)|Verbose|Запуск разрешения %1, выполняемого сопоставителем DataContract.|Сериализация|  
|[5008 — DCGenWriterStart](5008-dcgenwriterstart.md)|Verbose|Запуск создания модуля записи %1 для %2, выполняемого контрактом DataContract.|Сериализация|  
|[5009 — DCGenWriterStop](5009-dcgenwriterstop.md)|Verbose|Остановка создания модуля записи, выполняемого контрактом DataContract.|Сериализация|  
|[5010 — DCGenReaderStart](5010-dcgenreaderstart.md)|Verbose|Запуск создания модуля чтения %1 для %2, выполняемого контрактом DataContract.|Сериализация|  
|[5011 — DCGenReaderStop](5011-dcgenreaderstop.md)|Verbose|Остановка создания, выполняемого контрактом DataContract.|Сериализация|  
|[5012 — DCJsonGenReaderStart](5012-dcjsongenreaderstart.md)|Verbose|Запуск создания модуля чтения %1 для %2, выполняемого JSON.|Сериализация|  
|[5013 — DCJsonGenReaderStop](5013-dcjsongenreaderstop.md)|Verbose|Остановка создания модуля чтения, выполняемого JSON.|Сериализация|  
|[5014 — DCJsonGenWriterStart](5014-dcjsongenwriterstart.md)|Verbose|Запуск создания модуля записи %1 для %2, выполняемого JSON.|Сериализация|  
|[5015 — DCJsonGenWriterStop](5015-dcjsongenwriterstop.md)|Verbose|Остановка модуля записи, создаваемого JSON.|Сериализация|  
|[5016 — GenXmlSerializableStart](5016-genxmlserializablestart.md)|Verbose|Запуск создания сериализуемого XML для «%1».|Сериализация|  
|[5017 — GenXmlSerializableStop](5017-genxmlserializablestop.md)|Verbose|Остановка создания сериализуемого XML.|Сериализация|  
|[5203 — JsonMessageDecodingStart](5203-jsonmessagedecodingstart.md)|Verbose|JsonMessageEncoder начал расшифровку сообщения.|Канал|  
|[5204 — JsonMessageEncodingStart](5204-jsonmessageencodingstart.md)|Verbose|JsonMessageEncoder начал кодирование сообщения.|Канал|  
|[5402 — TokenValidationStarted](5402-tokenvalidationstarted.md)|Verbose|Запущена проверка SecurityToken (тип «%1» и идентификатор «%2»).|Безопасность|  
|[5403 — TokenValidationSuccess](5403-tokenvalidationsuccess.md)|Verbose|Проверка SecurityToken (тип «%1» и идентификатор «%2») выполнена успешно.|Безопасность|  
|[5404 — TokenValidationFailure](5404-tokenvalidationfailure.md)|Ошибка|Сбой при проверке SecurityToken (тип «%1» и идентификатор «%2»). %3|Безопасность|  
|[5405 — GetIssuerNameSuccess](5405-getissuernamesuccess.md)|Verbose|Получение имени поставщика %1 из tokenId:%2 выполнено успешно.|Безопасность|  
|[5406 — GetIssuerNameFailure](5406-getissuernamefailure.md)|Ошибка|Ошибка при получении имени поставщика из tokenId:%1.|Безопасность|  
|[5600 — FederationMessageProcessingStarted](5600-federationmessageprocessingstarted.md)|Verbose|Запущена обработка сообщений федерации.|Безопасность|  
|[5601 — FederationMessageProcessingSuccess](5601-federationmessageprocessingsuccess.md)|Verbose|Обработка сообщений федерации успешно завершена.|Безопасность|  
|[5602 — FederationMessageCreationStarted](5602-federationmessagecreationstarted.md)|Verbose|Запущено создание сообщения федерации из формы POST.|Безопасность|  
|[5603 — FederationMessageCreationSuccess](5603-federationmessagecreationsuccess.md)|Verbose|Создание сообщения федерации из формы POST успешно завершено.|Безопасность|  
|[5604 — SessionCookieReadingStarted](5604-sessioncookiereadingstarted.md)|Verbose|Запущено чтение токена сеанса из файла cookie сеанса.|Безопасность|  
|[5605 — SessionCookieReadingSuccess](5605-sessioncookiereadingsuccess.md)|Verbose|Чтение токена сеанса из файла cookie сеанса выполнено успешно.|Безопасность|  
|[5606 — PrincipalSettingFromSessionTokenStarted](5606-principalsettingfromsessiontokenstarted.md)|Verbose|Запущена установка субъекта из токена сеанса.|Безопасность|  
|[5607 — PrincipalSettingFromSessionTokenSuccess](5607-principalsettingfromsessiontokensuccess.md)|Verbose|Установка субъекта из токена сеанса выполнена успешно.|Безопасность|  
|[57393 — AppDomainUnload](57393-appdomainunload.md)|Сведения|Выгрузка AppDomain. AppDomain.FriendlyName %1, ProcessName %2, ProcessId %3.|Инфраструктура|  
|[57394 — HandledException](57394-handledexception.md)|Сведения|Обработка исключения.|Инфраструктура|  
|[57395 — ShipAssertExceptionMessage](57395-shipassertexceptionmessage.md)|Ошибка|Произошла непредвиденная ошибка. Приложения не должны обрабатывать эту ошибку. В целях диагностики приводится сообщение на английском языке, связанное с ошибкой: %1.|Инфраструктура|  
|[57396 — ThrowingException](57396-throwingexception.md)|Предупреждение|Создание исключения. Источник %1.|Инфраструктура|  
|[57397 — UnhandledException](57397-unhandledexception.md)|Critical|Необработанное исключение.|Инфраструктура|  
|[57399 — TraceCodeEventLogCritical](57399-tracecodeeventlogcritical.md)|Critical|Записано в журнал событий.|Инфраструктура|  
|[57400 — TraceCodeEventLogError](57400-tracecodeeventlogerror.md)|Ошибка|Записано в журнал событий.|Инфраструктура|  
|[57401 — TraceCodeEventLogInfo](57401-tracecodeeventloginfo.md)|Сведения|Записано в журнал событий.|Инфраструктура|  
|[57402 — TraceCodeEventLogVerbose](57402-tracecodeeventlogverbose.md)|Verbose|Записано в журнал событий.|Инфраструктура|  
|[57403 — TraceCodeEventLogWarning](57403-tracecodeeventlogwarning.md)|Предупреждение|Записано в журнал событий.|Инфраструктура|  
|[57404 — HandledExceptionWarning](57404-handledexceptionwarning.md)|Предупреждение|Обработка исключения.|Инфраструктура|  
|[62326 — HttpHandlerPickedForUrl](62326-httphandlerpickedforurl.md)|Сведения|URL-адрес «%1» содержит документ XAML с типом корневого элемента «%2». Выбран тип обработчика HTTP-данных «%3» для обслуживания всех запросов по этому URL-адресу.|WebHost|
