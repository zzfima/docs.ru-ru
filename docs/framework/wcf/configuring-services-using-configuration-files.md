---
title: Настройка служб с использованием файлов конфигурации
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: 29792726567373c907898cf6ced9891577f11588
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141625"
---
# <a name="configuring-services-using-configuration-files"></a>Настройка служб с использованием файлов конфигурации
Настройка службы Windows Communication Foundation (WCF) с помощью файла конфигурации обеспечивает гибкость предоставления данных о поведении конечных точек и служб в точке развертывания, а не во время разработки. В этой теме представлено описание основных доступных методов.  
  
 Службу WCF можно настроить с помощью технологии настройки .NET Framework. Чаще всего XML-элементы добавляются в файл Web. config для сайта службы IIS (IIS), на котором размещается служба WCF. Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер. Кроме того, в состав WCF входит несколько предоставляемых системой элементов, которые позволяют быстро выбрать наиболее простые функции для службы. Начиная с .NET Framework 4, WCF поставляется с новой моделью конфигурации по умолчанию, которая упрощает требования к конфигурации WCF. Если не указать конфигурацию WCF для конкретной службы, среда выполнения автоматически настроит службу с помощью некоторых стандартных конечных точек, а также привязки или поведения по умолчанию. На практике написание конфигурации является основной частью программирования приложений WCF.  
  
 Дополнительные сведения см. в разделе [Настройка привязок для служб](configuring-bindings-for-wcf-services.md). Список наиболее часто используемых элементов см. в разделе привязки, [предоставляемые системой](system-provided-bindings.md). Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](./samples/simplified-configuration-for-wcf-services.md).  
  
> [!IMPORTANT]
> При развертывании сценариев параллельного выполнения, в которых развернуты две различные версии службы, необходимо указывать частичные имена сборок, на которые ссылаются файлы конфигурации. Это связано с тем, что файл конфигурации совместно используется всеми версиями службы, которые могут выполняться под управлением различных версий платформы .NET Framework.  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a>System.Configuration: Web.config и App.config  
 WCF использует систему конфигурации System. Configuration .NET Framework.  
  
 При настройке службы в Visual Studio используйте файл Web. config или файл App. config, чтобы указать параметры. Выбор имени файла конфигурации определяется выбранной для службы средой размещения. Если служба размещается с помощью IIS, используйте файл Web.config. Если служба размещается с помощью другой среды размещения, используйте файл App.config.  
  
 В Visual Studio файл с именем App. config используется для создания окончательного файла конфигурации. Окончательное имя, которое фактически используется для конфигурации, зависит от имени сборки. Например, сборка с именем "Cohowinery.exe" имеет имя окончательного файла конфигурации "Cohowinery.exe.config". Однако следует изменить только файл App.config. Изменения, внесенные в это файл, автоматически вносятся в окончательный файл конфигурации приложения во время компиляции.  
  
 При использовании файла App.config система конфигурации объединяет файл App.config с содержимым файла Machine.config, когда запускается приложение и применяется конфигурация. Этот механизм позволяет определить параметры в рамках всего компьютера в файле Machine.config. Файл App.config можно использовать для переопределения параметров файла Machine.config. Также предусмотрена возможность блокировки в параметрах файла Machine.config согласно привычной работе. Если используется файл конфигурации Web.config, то система объединяет файлы Web.config во всех родительских каталогах вплоть до каталога приложения в применяемой конфигурации. Дополнительные сведения о конфигурации и параметрах приоритетов см. в разделе разделы в пространстве имен <xref:System.Configuration>.  
  
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
  
### <a name="the-services-element"></a>Элемент > служб \<Services  
 Элемент `services` содержит спецификации для всех служб, которые размещает приложение. Начиная с упрощенной модели конфигурации в .NET Framework 4, этот раздел является необязательным.  
  
 [службы \<](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a>Элемент > службы \<  
 Каждая служба имеет следующие атрибуты:  
  
- `name` Определяет тип, обеспечивающий реализацию контракта службы. Это полное имя, состоящее из пространства имен, точки и имени типа, например `"MyNameSpace.myServiceType"`.  
  
- `behaviorConfiguration` Задает имя одного из элементов `behavior` , найденных в `behaviors` . Заданное поведение управляет действиями, например, разрешает ли служба олицетворение. Если значением является пустое имя, или объект `behaviorConfiguration` не указан, то в службу добавляется набор поведений службы по умолчанию.  
  
- [> службы \<](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a>Элемент > \<конечной точки  
 Для каждой конечной точки требуется адрес, привязка и контракт, представленные следующими атрибутами:  
  
- `address` Задает универсальный код ресурса (URI) службы, который может быть абсолютным адресом или адресом, указанным относительно базового адреса службы. Если задана пустая строка, это означает, что конечная точка доступна по базовому адресу, который указывается при создании <xref:System.ServiceModel.ServiceHost> для службы.  
  
- `binding` Как правило, задает предоставляемую системой привязку типа <xref:System.ServiceModel.WSHttpBinding>, но также может задавать определяемую пользователем привязку. Заданная привязка определяет используемый тип транспорта, безопасности и кодирования, а также поддерживаются ли или включены ли надежные сеансы, транзакции или потоковая передача.  
  
- `bindingConfiguration` Если требуется изменить значения привязки по умолчанию, можно настроить соответствующий элемент `binding` в элементе `bindings` . Этому атрибуту должно быть присвоено то же значение, что и атрибуту `name` элемента `binding` , который используется для изменения значений по умолчанию. Если имя не задано, или в привязке не задан объект `bindingConfiguration` , то в конечной точке используется привязка по умолчанию типа привязки.  
  
- `contract` Задает интерфейс, определяющий контракт. Это интерфейс, реализованный в типе CLR, который задан атрибутом `name` элемента `service` .  
  
- [Конечная точка\<](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a>\<привязок > элемента  
 Элемент `bindings` содержит спецификации для всех привязок, которые могут использоваться любой конечной точкой, заданной в любой службе.  
  
 [привязки\<](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a>Элемент > привязки \<  
 Элемент `binding` , содержащиеся в элементе `bindings` , могут являться одной из предоставленных системой привязок (см. раздел [System-Provided Bindings](system-provided-bindings.md)) или пользовательской привязкой (см. раздел [Custom Bindings](./extending/custom-bindings.md)). Элемент `binding` имеет атрибут `name` , сопоставляющий привязку с конечной точкой, заданной в атрибуте `bindingConfiguration` элемента `endpoint` . Если имя не указано, то привязка будет соответствовать значению по умолчанию для этого типа привязки.  
  
Дополнительные сведения о настройке служб и клиентов см. в разделе [Настройка служб WCF](configuring-services.md).
  
 [> привязки \<](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a>\<поведения > элемента  
 Это элемент контейнера для элементов `behavior` , задающих поведение службы.  
  
 [\<поведений >](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a>\<поведение > элемента  
 Каждый элемент `behavior` определяется атрибутом `name` и предоставляет либо предоставляемое системой поведение, например <`throttling`>, либо пользовательское поведение. Если имя не задано, то элемент behavior будет соответствовать поведению по умолчанию для службы или конечной точки.  
  
 [\<поведение >](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a>Практическое руководство. Конфигурации привязок и поведения  
 WCF упрощает совместное использование конфигураций между конечными точками с помощью эталонной системы в конфигурации. Вместо того, чтобы непосредственно назначать значения конфигурации для конечной точки, значения конфигурации, относящиеся к привязке, группируются в элементах `bindingConfiguration` в разделе `<binding>` . Конфигурация привязок представляет собой именованную группу параметров привязки. Конечные точки могут ссылаться на `bindingConfiguration` по имени.  
  
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
  
 `name` для `bindingConfiguration` задано в элементе `<binding>` . `name` должен быть уникальной строкой в области действия типа привязки — в данном случае [< basicHttpBinding\>](../configure-apps/file-schema/wcf/basichttpbinding.md)или пустое значение для ссылки на привязку по умолчанию. Конечная точка содержит ссылки на конфигурацию, задавая для этой строки атрибут `bindingConfiguration` .  
  
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
  
 Файл `~\Web.config` имеет следующее содержимое:  
  
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
  
 Можно также очистить коллекции поведения с помощью тега \<Clear > и удалить отдельные поведения из коллекции с помощью \<удалить > тег. Например, действие следующих двух конфигураций приведет к тому, что в дочерней службе будет только поведение serviceMetadata:  
  
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
  
 Слияние поведения работает в среде размещения IIS, в которой файлы Web. config объединяются иерархически с корневым файлом Web. config и Machine. config. Но он также работает в среде приложения, где файл Machine. config может объединяться с файлом App. config.  
  
 Слияние поведений применяется в конфигурациях как к поведениям конечных точек, так и к поведениям служб.  
  
 Если коллекция дочерних поведений содержит поведение, которое уже определено в коллекции родительских поведений, то дочернее поведение переопределяет родительское. Таким образом, если родительская коллекция поведения `<serviceMetadata httpGetEnabled="False" />`, а Дочерняя коллекция поведения `<serviceMetadata httpGetEnabled="True" />`, дочернее поведение будет переопределять родительское поведение в коллекции поведения, а Хттпжетенаблед — «true».  
  
## <a name="see-also"></a>См. также

- [Упрощенная конфигурация](simplified-configuration.md)
- [Настройка служб WCF](configuring-services.md)
- [> службы \<](../configure-apps/file-schema/wcf/service.md)
- [> привязки \<](../configure-apps/file-schema/wcf/bindings.md)
