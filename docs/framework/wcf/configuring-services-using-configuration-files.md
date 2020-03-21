---
title: Настройка служб с использованием файлов конфигурации
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: caf6e238ca286e5e712c0273e10502655fd7ff4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174801"
---
# <a name="configuring-services-using-configuration-files"></a>Настройка служб с использованием файлов конфигурации
Настройка службы Windows Communication Foundation (WCF) с файлом конфигурации позволяет обеспечить гибкость в предоставлении данных конечной точки и поведения служб в момент развертывания, а не во время проектирования. В этой теме представлено описание основных доступных методов.  
  
 Услуга WCF настраивается с использованием технологии конфигурации .NET Framework. Чаще всего элементы XML добавляются в файл Web.config для сайта Интернет-информационных служб (IIS), на котором размещена служба WCF. Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер. Кроме того, WCF включает в себя несколько системных элементов, которые позволяют быстро выбрать самые основные функции для службы. Начиная с .NET Framework 4, WCF поставляется с новой моделью конфигурации по умолчанию, которая упрощает требования конфигурации WCF. Если вы не предоставляете конфигурацию WCF для конкретной службы, время выполнения автоматически настраивает службу с некоторыми стандартными конечными точками и связыванием/поведением по умолчанию. На практике настройка написания является важной частью программирования приложений WCF.  
  
 Для получения дополнительной информации [см.](configuring-bindings-for-wcf-services.md) Для списка наиболее часто используемых элементов [см.](system-provided-bindings.md) Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](./samples/simplified-configuration-for-wcf-services.md).  
  
> [!IMPORTANT]
> При развертывании сценариев параллельного выполнения, в которых развернуты две различные версии службы, необходимо указывать частичные имена сборок, на которые ссылаются файлы конфигурации. Это связано с тем, что файл конфигурации совместно используется всеми версиями службы, которые могут выполняться под управлением различных версий платформы .NET Framework.  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a>System.Configuration: Web.config и App.config  
 WCF использует систему конфигурации System.Configuration рамочного соглашения .NET.  
  
 При настройке службы в Visual Studio используйте файл Web.config или файл App.config для указания настроек. Выбор имени файла конфигурации определяется выбранной для службы средой размещения. Если служба размещается с помощью IIS, используйте файл Web.config. Если служба размещается с помощью другой среды размещения, используйте файл App.config.  
  
 В Visual Studio файл под названием App.config используется для создания файла окончательной конфигурации. Окончательное имя, которое фактически используется для конфигурации, зависит от имени сборки. Например, сборка с именем "Cohowinery.exe" имеет имя окончательного файла конфигурации "Cohowinery.exe.config". Однако следует изменить только файл App.config. Изменения, внесенные в это файл, автоматически вносятся в окончательный файл конфигурации приложения во время компиляции.  
  
 При использовании файла App.config система конфигурации объединяет файл App.config с содержимым файла Machine.config, когда запускается приложение и применяется конфигурация. Этот механизм позволяет определить параметры в рамках всего компьютера в файле Machine.config. Файл App.config можно использовать для переопределения параметров файла Machine.config. Также предусмотрена возможность блокировки в параметрах файла Machine.config согласно привычной работе. Если используется файл конфигурации Web.config, то система объединяет файлы Web.config во всех родительских каталогах вплоть до каталога приложения в применяемой конфигурации. Для получения дополнительной информации о конфигурации и <xref:System.Configuration> приоритетах настройки см.  
  
## <a name="major-sections-of-the-configuration-file"></a>Основные разделы файла конфигурации  
 Основные разделы файла конфигурации включают в себя следующие элементы.  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!-- Define the service endpoints. This section is optional in the new  
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
> Разделы привязок и поведения являются необязательными и указываются только при необходимости.  
  
### <a name="the-services-element"></a>Услуги \<> Элемент  
 Элемент `services` содержит спецификации для всех служб, которые размещает приложение. Начиная с упрощенной модели конфигурации в .NET Framework 4, этот раздел является необязательным.  
  
 [\<услуги>](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a>Обслуживание \<> Элемент  
 Каждая служба имеет следующие атрибуты:  
  
- `name`. Определяет тип, обеспечивающий реализацию контракта службы. Это полное имя, состоящее из пространства имен, точки и имени типа, Например, `"MyNameSpace.myServiceType"`.  
  
- `behaviorConfiguration`. Задает имя одного из элементов `behavior` , найденных в `behaviors` . Заданное поведение управляет действиями, например, разрешает ли служба олицетворение. Если значением является пустое имя, или объект `behaviorConfiguration` не указан, то в службу добавляется набор поведений службы по умолчанию.  
  
- [\<сервис>](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a>Конечная \<точка> Элемент  
 Для каждой конечной точки требуется адрес, привязка и контракт, представленные следующими атрибутами:  
  
- `address`. Задает универсальный код ресурса (URI) службы, который может быть абсолютным адресом или адресом, указанным относительно базового адреса службы. Если задана пустая строка, это означает, что конечная точка доступна по базовому адресу, который указывается при создании <xref:System.ServiceModel.ServiceHost> для службы.  
  
- `binding`. Как правило, задает предоставляемую системой привязку типа <xref:System.ServiceModel.WSHttpBinding>, но также может задавать определяемую пользователем привязку. Заданная привязка определяет используемый тип транспорта, безопасности и кодирования, а также поддерживаются ли или включены ли надежные сеансы, транзакции или потоковая передача.  
  
- `bindingConfiguration`. Если требуется изменить значения привязки по умолчанию, можно настроить соответствующий элемент `binding` в элементе `bindings` . Этому атрибуту должно быть присвоено то же значение, что и атрибуту `name` элемента `binding` , который используется для изменения значений по умолчанию. Если имя не задано, или в привязке не задан объект `bindingConfiguration` , то в конечной точке используется привязка по умолчанию типа привязки.  
  
- `contract`. Задает интерфейс, определяющий контракт. Это интерфейс, реализованный в типе CLR, который задан атрибутом `name` элемента `service` .  
  
- [\<>](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a>Привязки \<> Элемент  
 Элемент `bindings` содержит спецификации для всех привязок, которые могут использоваться любой конечной точкой, заданной в любой службе.  
  
 [\<привязки>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a>Связывающая \<> элемент  
 Элемент `binding` , содержащиеся в элементе `bindings` , могут являться одной из предоставленных системой привязок (см. раздел [System-Provided Bindings](system-provided-bindings.md)) или пользовательской привязкой (см. раздел [Custom Bindings](./extending/custom-bindings.md)). Элемент `binding` имеет атрибут `name` , сопоставляющий привязку с конечной точкой, заданной в атрибуте `bindingConfiguration` элемента `endpoint` . Если имя не указано, то привязка будет соответствовать значению по умолчанию для этого типа привязки.  
  
Для получения дополнительной информации о настройке услуг и клиентов, [см.](configuring-services.md)
  
 [\<связывающая>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a>Поведение \<> Элемент  
 Это элемент контейнера для элементов `behavior` , задающих поведение службы.  
  
 [\<поведение>](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a>Поведение \<> Элемент  
 Каждый `behavior` элемент идентифицируется атрибутом `name` и обеспечивает либо системное поведение, например <`throttling`>, либо пользовательское поведение. Если имя не задано, то элемент behavior будет соответствовать поведению по умолчанию для службы или конечной точки.  
  
 [\<поведение>](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a>Практическое руководство. Конфигурации привязок и поведения  
 WCF упрощает совместное использование конфигураций между конечными точками с помощью справочной системы в конфигурации. Вместо того, чтобы непосредственно назначать значения конфигурации для конечной точки, значения конфигурации, относящиеся к привязке, группируются в элементах `bindingConfiguration` в разделе `<binding>` . Конфигурация привязок представляет собой именованную группу параметров привязки. Конечные точки могут ссылаться на `bindingConfiguration` по имени.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!-- Default binding for basicHttpBinding -->  
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
  
 `name` для `bindingConfiguration` задано в элементе `<binding>` . Должна `name` быть уникальная строка в пределах типа связывания , в данном случае [<basicHttpBinding,\>](../configure-apps/file-schema/wcf/basichttpbinding.md)или пустое значение для обозначения привязки по умолчанию. Конечная точка содержит ссылки на конфигурацию, задавая для этой строки атрибут `bindingConfiguration` .  
  
 `behaviorConfiguration` реализуется аналогичным образом, как показано в следующем примере.  
  
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
  
 Заметьте, что в службу добавляет по умолчанию набор поведений службы. Эта система обеспечивает для конечных точек совместные общие конфигурации, не переопределяя параметры. Если требуется область на уровне компьютера, создайте конфигурацию привязки или поведения в файле Machine.config. Параметры конфигурации указаны во всех файлах App.config. [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) упрощает создание конфигураций.  
  
## <a name="behavior-merge"></a>Слияние поведений  
 Функция слияния поведений упрощает управление поведениями в ситуациях, когда должен постоянно использоваться набор общих поведений. Эта функция позволяет задавать поведения на разных уровнях иерархии конфигурации, а также настраивать наследование службами поведений от нескольких уровней иерархии конфигурации. Проиллюстрируем это следующим образом: предположим, что в IIS имеется следующая структура виртуальных каталогов:  
  
 `~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc`
  
 И `~\Web.config` ваш файл имеет следующее содержание:  
  
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
  
 Кроме того, имеется дочерний файл Web.config, расположенный в папке ~\Child\Web.config, со следующим содержимым:  
  
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
  
 Служба, расположенная в ~\Child\Service.svc, будет действовать таким образом, как будто бы для нее заданы и поведение serviceDebug, и поведение serviceMetadata. У службы, расположенной в ~\Service.svc, будет присутствовать только поведение serviceDebug behavior. В этой ситуации две коллекции поведений с одним и тем же именем (в данном случае пустой строкой) объединяются.  
  
 Вы также можете очистить коллекции поведения, используя четкий \<тег> \<и удалить отдельные поведения из коллекции с помощью> тега удаления. Например, действие следующих двух конфигураций приведет к тому, что в дочерней службе будет только поведение serviceMetadata:  
  
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
  
 Слияние поведений проводится для безымянных коллекций поведений (как показано выше), а также для именованных коллекций поведений.  
  
 Слияние поведения работает в среде хостинга IIS, в которой файлы Web.config сливаются иерархически с корневым файлом Web.config и machine.config. Но он также работает в среде приложения, где machine.config может слиться с файлом App.config.  
  
 Слияние поведений применяется в конфигурациях как к поведениям конечных точек, так и к поведениям служб.  
  
 Если коллекция дочерних поведений содержит поведение, которое уже определено в коллекции родительских поведений, то дочернее поведение переопределяет родительское. Таким образом, если `<serviceMetadata httpGetEnabled="False" />` родительское собрание поведения `<serviceMetadata httpGetEnabled="True" />`было и собрание поведения ребенка было, поведение ребенка будет переопределять поведение родителей в коллекции поведения и httpGetEnabled будет "истинным".  
  
## <a name="see-also"></a>См. также раздел

- [Упрощенная конфигурация](simplified-configuration.md)
- [Настройка wCF-сервисов](configuring-services.md)
- [\<сервис>](../configure-apps/file-schema/wcf/service.md)
- [\<связывающая>](../configure-apps/file-schema/wcf/bindings.md)
