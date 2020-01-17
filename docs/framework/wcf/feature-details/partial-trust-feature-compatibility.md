---
title: Совместимость возможностей частичного доверия
ms.date: 03/30/2017
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
ms.openlocfilehash: 3e0f1c2f673d4ba603df7da431d10c211cf779ac
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212126"
---
# <a name="partial-trust-feature-compatibility"></a>Совместимость возможностей частичного доверия
Windows Communication Foundation (WCF) поддерживает ограниченное подмножество функциональных возможностей при работе в среде с частичным доверием. Дополнительные сведения о различных функциях, поддерживаемых при работе с частичным доверием, которые разработаны на базе определенного набора сценариев, см. в разделе [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md) .  
  
## <a name="minimum-permission-requirements"></a>Минимальные требования к разрешениям  
 WCF поддерживает подмножество функций в приложениях, работающих с одним из следующих стандартных именованных наборов разрешений:  
  
- Разрешения среднего уровня доверия;  
  
- Набор разрешений зоны Интернета.  
  
 Попытка использовать WCF в частично доверенных приложениях с более ограниченными разрешениями может привести к исключениям безопасности во время выполнения.  
  
## <a name="contracts"></a>Контракты  
 При выполнении в частичном доверии контракты зависят от следующих ограничений:  
  
- Класс службы, реализующий интерфейс `[ServiceContract]` , должен иметь тип `public` и содержать конструктор типа `public` . Если он определяет методы `[OperationContract]` , они должны иметь тип `public`. Если вместо этого он реализует интерфейс `[ServiceContract]` , эти методы реализации могут быть явно заданы или иметь тип `private`при условии, что интерфейс `[ServiceContract]` имеет тип `public`;  
  
- При использовании атрибута `[ServiceKnownType]` указанный метод должен иметь тип `public`;  
  
- Классы`[MessageContract]` и их члены могут иметь тип `public`. Если класс `[MessageContract]` определен в сборке приложения, он может иметь тип `internal` и его члены будут также `internal` .  
  
## <a name="system-provided-bindings"></a>Привязки, предоставляемые системой  
 Типы <xref:System.ServiceModel.BasicHttpBinding> и <xref:System.ServiceModel.WebHttpBinding> полностью поддерживаются в среде с частичным доверием. Тип <xref:System.ServiceModel.WSHttpBinding> поддерживается только для режима безопасности транспорта.  
  
 Привязки, использующие транспорты, отличные от HTTP, такие как <xref:System.ServiceModel.NetTcpBinding>, <xref:System.ServiceModel.NetNamedPipeBinding>и <xref:System.ServiceModel.NetMsmqBinding>, не поддерживаются при выполнении в среде с частичным доверием.  
  
## <a name="custom-bindings"></a>Пользовательские привязки  
 Пользовательские привязки можно создавать и использовать в среде с частичным доверием, однако для них должны соблюдаться ограничения, указанные в данном разделе.  
  
### <a name="transports"></a>Транспорты  
 Допускается использование только элементов привязок транспортов <xref:System.ServiceModel.Channels.HttpTransportBindingElement> и <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
### <a name="encoders"></a>Кодировщики  
 Допускается использование следующих кодировщиков:  
  
- Текстовый кодировщик (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>);  
  
- Двоичный кодировщик (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>);  
  
- Кодировщик веб-сообщений (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>).  
  
 Кодировщики механизма оптимизации передачи сообщений (MTOM) не поддерживаются.  
  
### <a name="security"></a>по безопасности  
 Частично доверенные приложения могут использовать функции безопасности транспортного уровня WCF для защиты их взаимодействия. Безопасность уровня сообщений не поддерживается. Настройка привязки на использование безопасности уровня сообщений вызовет исключение в среде выполнения.  
  
### <a name="unsupported-bindings"></a>Неподдерживаемые привязки  
 Не поддерживаются привязки, использующие надежный обмен сообщениями, транзакции и безопасность уровня сообщений.  
  
## <a name="serialization"></a>Сериализация  
 Оба типа <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Xml.Serialization.XmlSerializer> поддерживаются в среде с частичным доверием. При этом использование <xref:System.Runtime.Serialization.DataContractSerializer> зависит от следующих условий.  
  
- Все сериализуемые типы `[DataContract]` должны иметь тип `public`.  
  
- Все сериализуемые поля и свойства `[DataMember]` в типе `[DataContract]` должны быть открытыми и доступными для чтения и записи. Сериализация и десериализация полей, доступных [только для чтения](https://go.microsoft.com/fwlink/?LinkID=98854) , не поддерживаются при выполнении WCF в приложении с частичным доверием.  
  
- Модель программирования `[Serializable]`/ISerializable не поддерживается в среде с частичным доверием.  
  
- Известные типы должны быть заданы в коде или конфигурации уровня компьютера (файл machine.config). По соображениям безопасности известные типы нельзя задавать в конфигурации уровня приложения.  
  
- Типы, которые реализуют <xref:System.Runtime.Serialization.IObjectReference> , в среде с частичным доверием вызывают исключение.  
  
 Дополнительные сведения о безопасности при использовании [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) в частично доверенном приложении см. в разделе "Сериализация" статьи <xref:System.Runtime.Serialization.DataContractSerializer> .  
  
### <a name="collection-types"></a>Типы коллекций  
 Некоторые типы коллекций реализуют и <xref:System.Collections.Generic.IEnumerable%601> , и <xref:System.Collections.IEnumerable>. Примеры содержат типы, которые реализуют <xref:System.Collections.Generic.ICollection%601>. Такие типы позволяют создать открытую ( `public` ) реализацию метода `GetEnumerator()`и явную реализацию метода `GetEnumerator()`. В данном случае <xref:System.Runtime.Serialization.DataContractSerializer> вызывает открытую ( `public` ) реализацию метода `GetEnumerator()`, а не явную реализацию метода `GetEnumerator()`. Если все реализации метода `GetEnumerator()` являются явными и нет ни одной открытой ( `public` ), сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> вызовет метод `IEnumerable.GetEnumerator()`.  
  
 Для типов коллекций, когда WCF выполняется в среде с частичным доверием, если ни одна из `GetEnumerator()`ных реализаций не `public`или ни одна из них не является явной реализацией интерфейса, возникает исключение безопасности.  
  
### <a name="netdatacontractserializer"></a>NetDataContractSerializer  
 При работе с частичным доверием многие типы коллекций .NET Framework не поддерживаются <xref:System.Collections.Generic.List%601>, например <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602> , <xref:System.Collections.Hashtable> и <xref:System.Runtime.Serialization.NetDataContractSerializer> . У этих типов задан атрибут `[Serializable]` , который не поддерживается при работе с частичным доверием, о чем написано выше в разделе «Сериализация». Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> обрабатывает коллекции определенным образом, тем самым существует возможность обхода данного ограничения, а у сериализатора <xref:System.Runtime.Serialization.NetDataContractSerializer> такого механизма обхода нет.  
  
 Тип <xref:System.DateTimeOffset> не поддерживается сериализатором <xref:System.Runtime.Serialization.NetDataContractSerializer> при работе с частичным доверием.  
  
 Суррогат не может использоваться в <xref:System.Runtime.Serialization.NetDataContractSerializer> (с помощью механизма <xref:System.Runtime.Serialization.SurrogateSelector> ) при работе с частичным доверием. Обратите внимание, что данное ограничение относится к использованию суррогата, а не к его сериализации.  
  
## <a name="enabling-common-behaviors-to-run"></a>Включение выполнения общих поведений  
 Поведения служб или конечных точек, которые не помечены атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA), которые добавляются в раздел [\<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) файла конфигурации, не выполняются, если приложение выполняется в среде с частичным доверием и при этом не возникает исключение. Чтобы принудительно запустить общие поведения, необходимо выполнить одно из следующих условий:  
  
- Пометить общее поведение атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute> , чтобы оно могло выполняться при развертывании в приложении с частичным доверием. Обратите внимание, что на компьютере может быть установлен соответствующий раздел реестра, чтобы на нем не могли выполняться сборки, помеченные атрибутом APTCA. .  
  
- Проверить, что при развертывании приложения в качестве приложения с полным доверием, которое не может изменяться пользователям, параметры управления доступом для кода разрешают выполнение приложения в среде с частичным доверием. Если это так, поведение не выполняется и исключение не создается. Чтобы убедиться в этом, ознакомьтесь с параметром **LevelFinal** с помощью [Caspol. exe (средство политики управления доступом для кода)](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md).  
  
 Пример общего поведения см. в разделе [как заблокировать конечные точки на предприятии](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
## <a name="configuration"></a>Конфигурация  
 С одним исключением частично доверенный код может загружать разделы конфигурации WCF только в локальный файл `app.config`. Для загрузки разделов конфигурации WCF, которые ссылаются на разделы WCF в Machine. config или в корневом файле Web. config, требуется Конфигуратионпермиссион (без ограничений). Без этого разрешения ссылки на разделы конфигурации WCF (поведения, привязки) за пределами локального файла конфигурации приводят к возникновению исключения при загрузке конфигурации.  
  
 Одно из известных исключений — конфигурация типа для сериализации, как описано в разделе "Сериализация" данной статьи.  
  
> [!IMPORTANT]
> Расширения конфигурации поддерживаются только при запуске с полным уровнем доверия.  
  
## <a name="diagnostics"></a>Диагностика  
  
### <a name="event-logging"></a>Ведение журнала событий  
 При выполнении в частичном доверии поддерживается ограниченное ведение журнала событий. Только сбои активации служб, а также ошибки трассировки и ведения журналов записываются в журнал событий. Максимальное число событий, которые записываются процессом, равно 5, что позволяет предотвратить запись чрезмерного количества сообщений в журнал событий.  
  
### <a name="message-logging"></a>Ведение журналов сообщений  
 Ведение журнала сообщений не работает при запуске WCF в среде с частичным доверием. Если для частичного доверия включено ведение журнала сообщений, сбой активации службы не произойдет, однако сообщения записываться не будут.  
  
### <a name="tracing"></a>Трассировка  
 При выполнении в среде с частичным доверием доступна ограниченная функциональность трассировки. В элементе <`listeners`> в файле конфигурации доступны только те типы, которые можно добавить <xref:System.Diagnostics.TextWriterTraceListener> и новый <xref:System.Diagnostics.EventSchemaTraceListener>. Использование обычного типа <xref:System.Diagnostics.XmlWriterTraceListener> может привести к неполным или неверным записям.  
  
 Поддерживаются следующие источники трассировки:  
  
- <xref:System.ServiceModel>  
  
- <xref:System.Runtime.Serialization>  
  
- <xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors> и <xref:System.IdentityModel.Tokens>.  
  
 Следующие источники трассировки не поддерживаются:  
  
- CardSpace  
  
- <xref:System.IO.Log>  

- [System. ServiceModel. internal. трансактионбридже](https://docs.microsoft.com/previous-versions/aa346556(v=vs.110))]
  
 Не должны быть заданы следующие члены перечисления <xref:System.Diagnostics.TraceOptions> :  
  
- <xref:System.Diagnostics.TraceOptions.Callstack?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceOptions.ProcessId?displayProperty=nameWithType>  
  
 При использовании трассировки в среде с частичным доверием, убедитесь, что приложение обладает достаточными правами для хранения выходных данных прослушивателя трассировки. Например, при использовании <xref:System.Diagnostics.TextWriterTraceListener> для записи выходных данных трассировки в текстовый файл, убедитесь, что приложение имеет необходимое разрешение FileIOPermission, которое требуется для добавления записей в файл трассировки.  
  
> [!NOTE]
> Чтобы избежать переполнения файлов трассировки с повторяющимися ошибками, WCF отключает трассировку ресурса или действия после первой ошибки безопасности. Существует одна трассировка исключения для каждой неудачной попытки доступа к ресурсам, которая создается при первой попытке доступа к ресурсам или при первой попытке выполнения действия.  
  
## <a name="wcf-service-host"></a>Узел службы WCF  
 Узел службы WCF не поддерживает частичное доверие. Если вы хотите использовать службу WCF в режиме частичного доверия, не используйте шаблон проекта библиотеки службы WCF в Visual Studio для создания службы. Вместо этого создайте новый веб-сайт в Visual Studio, выбрав шаблон веб-узел службы WCF, который может размещать службу на веб-сервере, на котором поддерживается частичное доверие WCF.  
  
## <a name="other-limitations"></a>Другие ограничения  

  Как правило, WCF ограничивается вопросами безопасности, накладываемыми приложением размещения. Например, если WCF размещается в приложении браузера XAML (XBAP), оно подчиняется ограничениям XBAP, как описано в разделе [Windows Presentation Foundation безопасность частичного доверия](../../wpf/wpf-partial-trust-security.md).  
  
 При выполнении indifo2 в среде с частичным доверием не включаются следующие дополнительные возможности:  
  
- Инструментарий управления Windows (WMI)  
  
- Ведение журнала событий не в полном объеме (см. обсуждение в разделе **Диагностика** );  
  
- Счетчики производительности.  
  
 Использование функций WCF, которые не поддерживаются в среде с частичным доверием, может привести к возникновению исключений во время выполнения.  
  
## <a name="unlisted-features"></a>Отсутствующие функции  
 Лучший способ обнаружить недоступный фрагмент информации или действия при выполнении в среде с частичным доверием - попытка обращения к ресурсу или выполнение действия внутри блока `try` с последующим перехватом ( `catch` ) сбоя. Чтобы избежать переполнения файлов трассировки с повторяющимися ошибками, WCF отключает трассировку ресурса или действия после первой ошибки безопасности. Существует одна трассировка исключения для каждой неудачной попытки доступа к ресурсам, которая создается при первой попытке доступа к ресурсам или при первой попытке выполнения действия.  
  
## <a name="see-also"></a>См. также:

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [Поддерживаемые сценарии развертывания](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)
- [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)
