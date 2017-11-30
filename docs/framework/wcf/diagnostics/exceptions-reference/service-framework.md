---
title: "Инфраструктура службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75f60b87-f80e-4377-ba7c-8e6becaa2b28
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 849857ae60137fe3286f2332358afabc3c26dcf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="service-framework"></a>Инфраструктура службы
В этом разделе перечислены все исключения, вызываемые данными инфраструктуры службы.  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|ABindingInstanceHasAlreadyBeenAssociatedTo1|Экземпляр привязки уже связан с прослушиванием указанного универсального кода ресурса. Если двум конечным точкам необходимо использовать общий код ListenUniform, им также требуется общий экземпляр объекта привязки. Две конфликтующие конечные точки были указаны в вызовах AddServiceEndpoint(), файле конфигурации, либо в комбинации вызовов AddServiceEndpoint() и файла конфигурации.|  
|AChannelServiceEndpointIsNull0|Конечная точка канала или службы не определена.|  
|AChannelServiceEndpointSContractSNameIsNull0|Имя контракта конечной точки канала/службы равно NULL или пусто.|  
|AChannelServiceEndpointSContractSNamespace0|Пространство имен контракта конечной точки канала/службы не определено.|  
|BaseAddressCannotHaveFragment|Базовый адрес не может содержать фрагмент URI.|  
|BaseAddressCannotHaveQuery|Базовый адрес не может содержать строку запроса URI.|  
|BaseAddressCannotHaveUserInfo|Базовый адрес не может содержать раздел с информацией о пользователе URI.|  
|BaseAddressDuplicateScheme|Коллекция уже содержит адрес с указанной схемой. В этой коллекции каждой схеме может соответствовать только один адрес.|  
|BaseAddressMustBeAbsolute|Только абсолютный URI можно использовать в качестве базового адреса.|  
|BindingDoesnTSupportAnyChannelTypes1|Указанная привязка не поддерживает создание типов каналов. Элементы пользовательской привязки расположены в стеке неправильно или в неверном порядке. Элемент Transport должен находиться в нижней части стека. Рекомендуемый порядок элементов привязки: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, Transport.|  
|BindingDoesnTSupportDuplexButContractRequires1|Контракту требуется свойство Duplex. Указанная привязка не поддерживает это или настроена неправильно.|  
|BindingDoesnTSupportOneWayButContractRequires1|Контракту требуется свойство OneWay. Указанная привязка не поддерживает это или настроена неправильно.|  
|BindingDoesnTSupportRequestReplyButContract1|Контракту требуется свойство Request или Reply. Указанная привязка не поддерживает это или настроена неправильно.|  
|BindingDoesnTSupportSessionButContractRequires1|Контракту требуется свойство Session.  Указанная привязка не поддерживает это или настроена неправильно.|  
|BindingDoesnTSupportTwoWayButContractRequires1|Контракту требуется свойство Two-Way (либо типа запрос-ответ, либо дуплексное). Указанная привязка не поддерживает это или настроена неправильно.|  
|BindingRequirementsAttributeDisallowsQueuedDelivery1|Атрибут DeliveryRequirementsAttribute запрещает метод QueuedDelivery. Привязка для конечной точки с указанным контрактом поддерживает его.|  
|BindingRequirementsAttributeRequiresQueuedDelivery1|Атрибут DeliveryRequirementsAttribute требует метод QueuedDelivery. Привязка для конечной точки с указанным контрактом не поддерживает это или настроена неправильно.|  
|channelDoesNotHaveADuplexSession0|Текущий канал не поддерживает закрытие выходных сеансов. Этот канал не реализует ISessionChannel\<IDuplexSession >.|  
|ClientRuntimeRequiresFormatter0|Указанный элемент ClientOperation требуется средство форматирования, так как параметры SerializeRequest и DeserializeReply не имеют одновременно значение false.|  
|CommunicationObjectAborted1|Указанный коммуникационный объект нельзя использовать для связи, так как он остановлен.|  
|CommunicationObjectAbortedStack2|Указанный коммуникационный объект нельзя использовать для связи, так как он остановлен: {1}|  
|CommunicationObjectBaseClassMethodNotCalled|Указанный коммуникационный объект переопределил виртуальную функцию {1}, однако не вызвал версию, заданную в базовом классе.|  
|ContractIsNotSelfConsistentItHasOneOrMore2|Указанный контракт имеет одну или несколько операций IsTerminating или non-IsInitiating. Свойству SessionMode не присвоено значение SessionMode.Required. Атрибуты IsInitiating и IsTerminating можно использовать только в контексте сеанса.|  
|CouldnTCreateChannelForChannelType2|Указанный тип канала был запрошен, однако указанная привязка не поддерживает это или настроена неправильно.|  
|DispatchRuntimeRequiresFormatter0|Указанный элемент DispatchOperation требуется средство форматирования, так как параметры DeserializeRequest и SerializeReply не имеют одновременно значение false.|  
|EndMethodsCannotBeDecoratedWithOperationContractAttribute|При использовании шаблона проектирования IAsyncResult метод End нельзя использовать с атрибутом OperationContractAttribute. С атрибутом OperationContractAttribute можно использовать только соответствующий метод Begin. Этот атрибут применяется к паре методов Begin-End.|  
|EndpointListenerRequirementsCannotBeMetBy3|IChannelListener для указанной привязки не может удовлетворить требованиям ChannelDispatcher, так как данный контракт требует поддержки одного из указанных типов канала. Привязка поддерживает только указанные типы каналов.|  
|EndpointsMustHaveAValidBinding0|Конечные точки должны иметь допустимую привязку.|  
|InvalidOrUnrecognizedAction|Обработка сообщения невозможна, так как указанное действие недопустимо или нераспознано.|  
|MultipleMebesInParameters|Обнаружено несколько элементов MessageEncodingBindingElement в BindingParameters контекста BindingContext. Привязка CustomBinding не может иметь несколько элементов MessageEncodingBindingElements. Удалите все элементы, кроме одного.|  
|MultipleStreamUpgradeProvidersInParameters|Обнаружено несколько элементов IStreamUpgradeProviderElement в BindingParameters контекста BindingContext. Привязка CustomBinding не может иметь несколько элементов IStreamUpgradeProviderElements. Удалите все элементы, кроме одного.|  
|NoChannelBuilderAvailable|Невозможно использовать привязку для создания производства канала или прослушивателя канала, поскольку в ней нет элемента TransportBindingElement. В каждой привязке должен присутствовать по меньшей мере один элемент привязки, наследуемый от TransportBindingElement.|  
|NotAllBindingElementsBuilt|Некоторые элементы данной привязки не были использовании при создании производства канала и прослушивателя канала. Элементы привязки расположены в неправильном порядке. Рекомендуемый порядок элементов привязки: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, Transport.  Последним должен быть элемент TransportBindingElement. Указанные элементы привязки не были созданы.|  
|RuntimeRequiresInvoker0|Операции отправки требуется средство вызова.|  
|ServiceHasZeroAppEndpoints|Указанная служба не имеет конечных точек приложения (не инфраструктурных). Это может быть связано с тем, что для данного приложения не найден файл конфигурации или в файле конфигурации не удалось найти элементы службы, соответствующие данному имени службы, или конечные точки не были определены в элементе службы.|  
|SFxActionMismatch|Не удается создать типизированное сообщение из-за несоответствия действия. Ожидается указанное действие, а происходит другое.|  
|SFxAnonymousTypeNotSupported|Указанную часть указанного сообщения нельзя экспортировать с помощью RPC или закодировать, так как она имеет анонимный тип.|  
|SFxBadMetadataLocationNoAppropriateBaseAddress|URL-адрес, указанный для ServiceMetadataBehavior посредством свойства ExternalMetadataLocation или атрибута externalMetadataLocation в разделе serviceMetadata конфигурации, является относительным URL-адресом, и нет базового адреса для его разрешения.|  
|SFxBadMetadataMustBePolicy|Необходимо предоставить XML-элемент политики, имеющий указанное имя и пространство имен. Данный XML-элемент имеет указанное имя и пространство имен.|  
|SFxBodyObjectTypeCannotBeInherited|Указанный тип не может наследовать из любого класса ничего, кроме объекта, используемого в качестве объекта тела в стиле RPC.|  
|SFxBodyObjectTypeCannotBeInterface|Указанный тип реализует указанный интерфейс, который не поддерживается объектом тела в стиле RPC.|  
|SFxCallbackBehaviorAttributeOnlyOnDuplex|Атрибут CallbackBehaviorAttribute может запускаться только в виде поведения конечной точки с дуплексным контрактом. Указанный контракт не является дуплексным и не содержит операций обратного вызова.|  
|SFxCallbackRequestReplyInOrder1|Ответ не может быть получен от этой операции до завершения обработки текущего сообщения. Если необходимо разрешить неупорядоченную обработку сообщений, задайте для ConcurrencyMode значение Reentrant или Multiple в указанном объекте.|  
|SfxCallbackTypeCannotBeNull|Для использования указанного контракта с DuplexChannelFactory в контракте должен быть указан допустимый контракт обратного вызова. Если в контракте указан контракт обратного вызова, используйте ChannelFactory вместо DuplexChannelFactory.|  
|SFxCannotGetMetadataFromLocation|Клиент MetadataExchangeClient может получить метаданные только из HTTP и HTTPS MetadataLocations. Он не может получить метаданные из указанного объекта.|  
|SFxCannotHttpGetMetadataFromAddress|Клиент MetadataExchangeClient может получить метаданные только из адресов HTTP или HTTPS при использовании режима MetadataExchangeClientMode HttpGet. Он не может получить метаданные из указанного объекта.|  
|SFxCannotImportAsParameters_Bare|Контракт генерации сообщений с указанной операцией не является ни RPC, ни упакованным документом.|  
|SFxCannotImportAsParameters_DifferentWrapperName|Контракт генерации сообщений с именем упаковщика указанного сообщения не соответствует значению по умолчанию.|  
|SFxCannotImportAsParameters_DifferentWrapperNs|Контракт генерации сообщений с пространством имен упаковщика указанного сообщения не соответствует значению по умолчанию.|  
|SFxCannotImportAsParameters_ElementIsNotNillable|Контракт генерации сообщений с указанным именем элемента из указанного пространства имен не отмечен как обнуляемый.|  
|SFxCannotImportAsParameters_HeadersAreUnsupported|Контракт генерации сообщений с указанным сообщением имеет заголовки.|  
|SFxCannotImportAsParameters_Message|Контракт генерации сообщений с указанной операцией имеет нетипизированное сообщение в качестве аргумента или возвращаемого типа.|  
|SFxCannotImportAsParameters_MessageHasProtectionLevel|Контракт генерации сообщений с указанным сообщением требует защиты.|  
|SFxCannotImportAsParameters_NamespaceMismatch|Контракт генерации сообщений с указанным пространством имен частей сообщения не соответствует значению по умолчанию.|  
|SFxCannotRequireBothSessionAndDatagram3|Указанный контракт задает параметр SessionMode.NotAllowed, другой указанный контракт задает параметр SessionMode.Required. Необходимо изменить одно из значений SessionMode или указать другой адрес (или ListenURI) для каждой конечной точки.|  
|SFxCannotSetExtensionsByIndex|Данная коллекция не поддерживает задание расширений по индексу. Используйте методы InsertItem или RemoveItem.|  
|SFxChannelDispatcherDifferentHost0|ChannelDispatcher в настоящее время не закреплен за предоставленным объектом ServiceHost.|  
|SFxChannelDispatcherMultipleHost0|Не удается добавить ChannelDispatcher к более чем одному объекту ServiceHost.|  
|SFxChannelDispatcherNoHost0|Не удается открыть ChannelDispatcher, так как он не закреплен за объектом ServiceHost.|  
|SfxChannelFactoryDisposed|Нельзя открыть ChannelFactory, так как ChannelFactory уже освобожден. Необходимо повторно создать ChannelFactory перед его использованием.|  
|SFxChannelFactoryNoBinding|Нельзя открыть ChannelFactory, так как с его конечной точкой ни связана ни одна привязка. Задайте привязку с конструктором или свойство Endpoint.|  
|SFxChannelTerminated0|В данном канале уже была вызвана операция, отмеченная как IsTerminating, что привело к разрыву подключения канала. В канале больше нельзя вызвать операции. Для продолжения связи необходимо создать канал повторно.|  
|SFxCloseTimedOut1|Операция закрытия ServiceHost прервана по истечении указанного времени ожидания. Это может быть вызвано тем, что клиенту не удалось закрыть канал сеанса в течение заданного времени. Выделенное для этой операции время может быть частью более длинного времени ожидания.|  
|SfxCloseTimedOutWaitingForDispatchToComplete|Процесс закрытия прерван по истечении времени ожидания в ожидании завершения отправки службы.|  
|SFxCodeGenIsNotAssignableFrom|Не удается назначить указанный объект.|  
|SFxConfigChannelConfigurationNotFound|Не удается найти элемент конечной точки с указанным именем и контрактом в разделе конфигурации клиента ServiceModel.|  
|SFxConflictingGlobalElement|XML-элемент верхнего уровня с указанным именем в указанном пространстве имен не может ссылаться на указанный тип. Он уже ссылается на другой тип. Используйте другое имя операции или атрибут MessageBodyAttribute, чтобы указать другое имя для сообщения или частей сообщения.|  
|SFxContractHasZeroInitiatingOperations|Контракт должен иметь не менее одной операции IsInitiating=true.|  
|SFxContractHasZeroOperations|Контракт должен иметь не менее одной операции.|  
|SFxContractInheritanceRequiresInterfaces|Класс службы указанного типа одновременно определяет ServiceContract и наследует ServiceContract от указанного типа. Наследование контракта можно использовать только между типами интерфейсов. Если класс имеет атрибут ServiceContractAttribute, то он должен быть в иерархии единственным типом с ServiceContractAttribute.  Перенесите атрибут ServiceContractAttribute указанного типа в отдельный интерфейс, который реализуется указанным типом.|  
|SFxCreateDuplexChannel1|Контракт обратного вызова указанного контракта не существует или не определяет ни одной операции. Если это не дуплексный контракт, используйте ChannelFactory вместо DuplexChannelFactory.|  
|SFxCreateDuplexChannelNoCallback|Перегрузка CreateChannel не может быть вызвана этим экземпляром DuplexChannelFactory. DuplexChannelFactory не был инициализирован с контекстом InstanceContext. Вызовите перегрузку CreateChannel, которая допускает InstanceContext.|  
|SFxCreateDuplexChannelNoCallback1|Перегрузка CreateChannel не может быть вызвана этим экземпляром DuplexChannelFactory. DuplexChannelFactory был инициализирован с некоторым типом, но без предоставления допустимого контекста InstanceContext. Вызовите перегрузку CreateChannel, которая допускает InstanceContext.|  
|SFxCreateDuplexChannelNoCallbackUserObject|Перегрузка CreateChannel не может быть вызвана этим экземпляром DuplexChannelFactory. Контекст InstanceContext, предоставленный производству DuplexChannelFactory, не содержит допустимого объекта UserObject.|  
|SFxCreateNonDuplexChannel1|ChannelFactory не поддерживает указанный контракт. ChannelFactory определяет контракт обратного вызова с одной или несколькими операциями. Используйте DuplexChannelFactory вместо ChannelFactory.|  
|SFxCustomBindingNeedsTransport1|В привязке CustomBinding из ServiceEndpoint с указанным контрактом отсутствует элемент TransportBindingElement. В каждой привязке должен присутствовать по меньшей мере один элемент привязки, наследуемый от TransportBindingElement.|  
|SFxCustomBindingWithoutTransport|Не удается вычислить схему для специальной привязки, так как в ней отсутствует элемент TransportBindingElement. В каждой привязке должен присутствовать по меньшей мере один элемент привязки, наследуемый от TransportBindingElement.|  
|SFxDataContractSerializerDoesNotSupportBareArray|DataContractSerializer не поддерживает коллекцию, заданную в указанном элементе.|  
|SFxDictionaryIsEmpty|Невозможно выполнить операцию, поскольку словарь пуст.|  
|SFxDocEncodedNotSupported|Ошибка при отражении указанного объекта. Document-Encoded не поддерживается. Задайте для Use значение Literal, а для Style - значение RPC.|  
|SFxDuplicateInitiatingActionAtSameVia|Эта служба имеет несколько конечных точек, выполняющих указанное прослушивание. Конечные точки совместно используют одно и то же инициирующее действие. Сообщения с этим действием будут пропущены, так как диспетчер не может определить правильную конечную точку для обработки такого сообщения.|  
|SFXEndpointBehaviorUsedOnWrongSide|Указанное поведение IEndpointBehavior нельзя использовать на сервере. Его можно применять только к клиентам.|  
|SFxEndpointNoMatchingScheme|Не удается найти базовый адрес, соответствующий указанной схеме для конечной точки с указанной привязкой. Заданы зарегистрированные схемы базовых адресов.|  
|SFxErrorCreatingMtomReader|При создании средства чтения для сообщения MTOM произошла ошибка.|  
|SFxErrorDeserializingFault|Сервер возвратил недопустимое сообщение об ошибке SOAP. Дополнительные сведения см. в разделе InnerException.|  
|SFxErrorDeserializingHeader|При десериализации одного из заголовков указанного сообщения произошла ошибка. Дополнительные сведения см. в разделе InnerException.|  
|SFxErrorReflectingOnMethod3|Ошибка при загрузке указанного атрибута указанного метода в указанном типе.  Дополнительные сведения см. в разделе InnerException.|  
|SFxErrorReflectingOnParameter4|Ошибка при загрузке указанного атрибута указанного параметра указанного метода в указанном типе. Дополнительные сведения см. в разделе InnerException.|  
|SFxErrorReflectingOnType2|Ошибка при загрузке указанного атрибута в указанном типе.  Дополнительные сведения см. в разделе InnerException.|  
|SFxErrorSerializingBody|При сериализации тела указанного сообщения произошла ошибка. Дополнительные сведения см. в разделе InnerException.|  
|SFxErrorSerializingHeader|При сериализации одного из заголовков указанного сообщения произошла ошибка. Дополнительные сведения см. в разделе InnerException.|  
|SFxExpectedIMethodCallMessage|Внутренняя ошибка. Сообщение должно быть допустимым IMethodCallMessage.|  
|SFxExportMustHaveType|Указанную часть указанной операции нельзя экспортировать, так как она не имеет допустимого типа CLR.|  
|SFxHeaderNotUnderstood|Сообщение не было обработано. Получатель данного сообщения не распознал указанный заголовок из указанного пространства имен. Эта ошибка обычно указывает, что отправитель сообщения включил протокол связи, который не может быть обработан получателем. Необходимо обеспечить совместимость конфигурации привязки клиента с привязкой службы.|  
|SFxHeadersAreNotSupportedInEncoded|Указанное сообщение не должно иметь заголовков, чтобы его можно было использовать в стиле кодировки RPC.|  
|SFxInconsistentWsdlOperationStyleInMessageParts|Все части сообщения в указанной операции должны содержать тип или элемент.|  
|SFxInconsistentWsdlOperationStyleInOperationMessages|Указанный стиль, полученный из сообщений в указанной операции, не соответствует указанному ожидаемому стилю, заданному с помощью привязок.|  
|SFxInvalidCallbackIAsyncResult|Интерфейс IAsyncResult не предоставлен или имеет неправильный тип.|  
|SFxInvalidMessageBody|OperationFormatter обнаружил недопустимое тело сообщения. Ожидался тип узла "Element" с указанным именем и пространством имен. Найден указанный тип узла с указанным именем и пространством имен.|  
|SFxInvalidMessageBodyEmptyMessage|OperationFormatter не удалось десериализовать какую-либо информацию из данного сообщения, так как сообщение пустое.|  
|SFxInvalidMessageBodyErrorDeserializingParameter|При попытке десериализации указанного параметра произошла ошибка. Дополнительные сведения см. в разделе InnerException.|  
|SFxInvalidMessageBodyErrorSerializingParameter|При попытке сериализации указанного параметра произошла ошибка. Указано сообщение InnerException.  Дополнительные сведения см. в разделе InnerException.|  
|SFxInvalidMessageBodyUnexpectedNode|При десериализации параметров обнаружен указанный непредвиденный узел в указанном пространстве имен.|  
|SFxInvalidMessageContractSignature|Указанная операция имеет параметр или возвращенный тип с атрибутом MessageContractAttribute. Чтобы представить сообщение запроса с помощью контракта сообщения, операция должна иметь один параметр с атрибутом MessageContractAttribute. Чтобы представить сообщение ответа с помощью контракта сообщения, возвращенное значение операции должно быть типом, имеющим атрибут MessageContractAttribute. Операция не должна иметь параметры out или ref.|  
|SFxInvalidReplyAction|В исходящем сообщении ответа для операции указано действие Action, однако в контракте для этой операции указано другое действие ReplyAction. Действие Action в сообщении должно соответствовать действию ReplyAction в контракте, или в контракте операции должно быть задано действие ReplyAction='*'.|  
|SFxInvalidRequestAction|В исходящем сообщении запроса для операции указано действие Action, однако в контракте для этой операции указано другое действие RequestAction. Действие Action в сообщении должно соответствовать действию RequestAction в контракте, или в контракте операции должно быть задано действие RequestAction='*'.|  
|SFxInvalidStaticOverloadCalledForDuplexChannelFactory1|Нельзя использовать статический метод CreateChannel с указанным контрактом, так как контракт определяет контракт обратного вызова. Используйте один из статических перегрузок CreateChannel на производстве DuplexChannelFactory\<TChannel >.|  
|SFxInvalidStreamInRequest|Чтобы запрос в указанной операции был потоком, операция должна иметь один параметр с типом Stream.|  
|SFxInvalidStreamInResponse|Чтобы ответ в указанной операции был потоком, операция должна иметь один выходной параметр или возвращенное значение с типом Stream.|  
|SFxInvalidStreamInTypedMessage|Чтобы использовать потоки в программной модели контракта сообщения, указанный тип должен иметь один член MessageBodyMember типа Stream.|  
|SFxInvalidUseOfPrimitiveOperationFormatter|Объекту PrimitiveOperationFormatter предоставлен параметр или возвращаемый тип, который он не поддерживает.|  
|SFxMessageContractBaseTypeNotValid|Указанный тип определяет MessageContract, но также является производным от другого указанного типа, который не определяет MessageContract. Все объекты в указанной иерархии наследования должны определить MessageContract.|  
|SFxMethodNotSupported1|Указанный метод не поддерживается для этого объекта. Это может произойти, если метод не помечен атрибутом OperationContractAttribute или если тип интерфейса не помечен атрибутом ServiceContractAttribute.|  
|SFxMethodNotSupportedByType2|Указанный тип реализации ServiceHost не реализует указанный контракт службы.|  
|SFxMethodNotSupportedOnCallback1|Указанный метод обратного вызова не поддерживается. Это может произойти, если метод не помечен атрибутом OperationContractAttribute или если его тип интерфейса не является целью ServiceContractAttribute объекта CallbackContract.|  
|SFxMismatchedOperationParent|Элемент DispatchOperation или ClientOperation можно добавить только к своему родительскому элементу DispatchRuntime или ClientRuntime соответственно.|  
|SFxNameCannotBeEmpty|Свойство Name не может быть пустой строкой.|  
|SfxNoTypeSpecifiedForParameter|Тип CLR не задан для параметра, что препятствует созданию данной операции.|  
|SFxOperationBehaviorAttributeOnlyOnServiceClass|Атрибут OperationBehaviorAttribute поддерживает только класс службы. Он не может применяться к интерфейсу ServiceContract. Указанный метод в указанном типе нарушает это правило.|  
|SFxOperationContractOnNonServiceContract|Указанный метод помечен атрибутом OperationContractAttribute, однако указанный включающий тип не помечен атрибутом ServiceContractAttribute. Атрибут OperationContractAttribute применим только к методам в типах ServiceContractAttribute или их типам CallbackContract.|  
|SFxParameterCountMismatch|Несоответствие между числом предоставленных аргументов и числом ожидаемых аргументов. В частности, указанный аргумент имеет указанное число элементов, а ожидаемый аргумент имеет другое указанное число элементов.|  
|SFxPartNameMustBeUniqueInRpc|Указанное имя части сообщения не является уникальным в сообщении RPC.|  
|SFxReplyActionMismatch3|Получено ответное сообщение для указанной операции с указанным действием. Однако код клиента требует другого действия.|  
|SFxRequestReplyNone|Получено сообщение с указанием адреса "None" в заголовке WS-Addressing ReplyTo или FaultTo. Эти значения недопустимы для операций типа запрос-ответ. Используйте одностороннюю операцию или включите ManualAddressing, если требуется поддерживать ReplyTo или FaultTo со значением "None".|  
|SFxRequestTimedOut1|Ответ на операцию запроса не получен в течение указанного времени ожидания. Выделенное время может быть частью более длинного времени ожидания. Это может быть связано с тем, что служба продолжает обрабатывать операцию, или что службе не удалось отправить ответное сообщение.|  
|SFxRequestTimedOut2|Ответ на операцию запроса, отправленную в указанное местоположение, не получен в течение указанного времени ожидания. Выделенное время может быть частью более длинного времени ожидания. Это может быть связано с тем, что служба продолжает обрабатывать операцию, или что службе не удалось отправить ответное сообщение.|  
|SFxSchemaDoesNotContainType|В схеме с указанным целевым пространством имен отсутствует тип с указанным именем.|  
|SfxServiceContractAttributeNotFound|Указанный тип контракта не имеет атрибута ServiceContractAttribute. Чтобы определить допустимый контракт, указанный тип должен иметь атрибут ServiceContractAttribute. Этот тип может быть интерфейсом контракта или классом службы.|  
|SFxServiceContractGeneratorConfigRequired|Чтобы создать информацию о конфигурации с помощью метода GenerateServiceEndpoint, экземпляр ServiceContractGenerator должен быть инициализирован допустимым объектом Configuration.|  
|SFxServiceHostBaseCannotAddEndpointAfterOpen|Невозможно добавить конечные точки после того, как ServiceHost находится в одном из следующих состояний:<br /><br /> -Открыт<br />— Сбой<br />-Завершено<br />-Закрыт|  
|SFxServiceHostBaseCannotAddEndpointWithoutDescription|Невозможно добавить конечные точки до инициализации свойства Description.|  
|SFxServiceMetadataBehaviorNoHttpBaseAddress|Свойство HttpGetEnabled объекта ServiceMetadataBehavior имеет значение true, а свойство HttpGetUrl является относительным адресом, но при этом отсутствует базовый HTTP-адрес. Задайте базовый HTTP-адрес или задайте абсолютный адрес для HttpGetUrl.|  
|SFxServiceMetadataBehaviorNoHttpsBaseAddress|Свойство HttpsGetEnabled объекта ServiceMetadataBehavior имеет значение true, а свойство HttpsGetUrl является относительным адресом, но при этом отсутствует базовый HTTPS-адрес. Задайте базовый HTTPS-адрес или задайте абсолютный адрес для HttpsGetUrl.|  
|SFxServiceMetadataBehaviorUrlMustBeHttpOrRelative|Код Url поведения должен быть относительным кодом Url или абсолютным кодом Url для указанной схемы. Указанный код URI является абсолютным для указанной схемы.|  
|SFxStreamRequestMessageClosed|Сообщение, содержащее этот поток, было закрыто. Потоки запросов становятся недоступными после возвращения операции службы.|  
|SFxStreamResponseMessageClosed|Сообщение, содержащее этот поток, было закрыто.|  
|SFxTerminateRequestProcessingException|Расширение в конвейере операций должно прекратить обработку этого сообщения.|  
|SFxTerminatingOperationAlreadyCalled1|По этому каналу больше нельзя отправлять сообщения, так как вызвана операция IsTerminating.|  
|SFxThrottleLimitMustBeGreaterThanZero0|Предел ограничителя должен быть больше нуля. Чтобы отключить его, установите значение Int32.MaxValue.|  
|SFxTypedOrUntypedMessageCannotBeMixedWithVoidInRpc|При использовании стиля с RPC-кодировкой нельзя использовать типы контрактов сообщений или тип System.ServiceModel.Channels.Message, если операция не имеет параметров или имеет возвращаемое значение void. Добавьте к указанной операции пустой тип контракта сообщения в качестве параметра или возвращаемого значения.|  
|SFxUserCodeThrewException|Указанная операция пользователя создала исключение, которое не было обработано в коде пользователя. Повторение проблемы может свидетельствовать об ошибке реализации указанного метода.|  
|SfxUseTypedMessageForCustomAttributes|Не удается сопоставить указанный параметр с параметром операции, так как требуются дополнительные атрибуты.|  
|SFxVersionMismatchInOperationContextAndMessage2|Невозможно добавить к сообщению исходящие заголовки, так как версия MessageVersion в OperationContext.Current не соответствует версии заголовка обрабатываемого сообщения.|  
|SFxWellKnownNonSingleton0|Чтобы использовать один из конструкторов ServiceHost, который принимает экземпляр службы, режиму InstanceContextMode службы необходимо присвоить значение InstanceContextMode.Single. Это можно сделать с помощью атрибута ServiceBehaviorAttribute. В противном случае воспользуйтесь конструкторами ServiceHost, которые принимают аргумент Type.|  
|SFxWrapperTypeHasMultipleNamespaces|Тип оболочки указанного сообщения не может быть защищен как тип контракта данных, так как он имеет несколько пространств имен. Используйте XmlSerializer.|  
|UriMustBeAbsolute|URI должен быть абсолютным.|
