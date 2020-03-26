---
title: Упрощенная конфигурация
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 4e316290c045b75896c61e36c1646440c18678e2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249634"
---
# <a name="simplified-configuration"></a>Упрощенная конфигурация
Настройка служб Windows Communication Foundation (WCF) может быть сложной задачей. Разных параметров много, и не всегда легко понять, какие настройки необходимы. В то время как файлы конфигурации повышают гибкость служб WCF, они также являются источником многих проблем, которые трудно найти. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] устраняет эти проблемы, предоставляя способ уменьшить размер и упростить конфигурацию службы.  
  
## <a name="simplified-configuration"></a>Упрощенная конфигурация  
 В файлах конфигурации wCF раздел `system.serviceModel` <`service`> содержит элемент <> для каждой размещенной службы. Элемент `service`> <содержит набор `endpoint` элементов> <, которые определяют конечные точки, выставленные для каждой службы, и опционально набор поведения службы. В `endpoint` <> элементы определяют адрес, связывание и контракт, выставленные в конечном пункте, а также опционально обязательную конфигурацию и поведение конечных точек. Раздел `system.serviceModel` <> также `behaviors` содержит элемент> <, который позволяет указать поведение службы или конечных точек. В следующем примере `system.serviceModel` показан <> раздел файла конфигурации.  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]Упрощает настройку службы WCF, удаляя требование к элементу <`service`>. Если вы не добавите <`service`> раздел или `service` не добавите какие-либо конечные точки в раздел> <и ваша служба не будет программно определять какие-либо конечные точки, то в ваш сервис автоматически добавляется набор конечных точек по умолчанию, по одному для каждого базового адреса службы и для каждого контракта, реализованного вашей службой. В каждой из этих конечных точек адрес конечной точки соответствует базовому адресу, привязка определяется схемой базового адреса, а контракт - службой. Если не нужно задавать конечные точки или поведения служб или изменять какие-либо параметры привязки, то указывать файл конфигурации служб не нужно вообще. Если служба реализует два контракта, а на узле включен транспорт по протоколам HTTP и TCP, то узел службы создаст четыре точки по умолчанию: по одной на каждый контракт для каждого транспорта. Чтобы создать по умолчанию конечные точки, узел службы должен знать, какие привязки использовать. Эти параметры указаны в `protocolMappings` разделе> `system.serviceModel` <в разделе <>. Раздел `protocolMappings` <> содержит список схем транспортных протоколов, отображаемых на обязательные типы. Узел службы использует переданные ему базовые адреса, чтобы определить, какую привязку использовать. В следующем примере `protocolMappings` используется элемент> <.  
  
> [!WARNING]
> Изменение элементов конфигурации по умолчанию, например привязок или поведений, может повлиять на службы, определенные на нижних уровнях иерархии конфигурации, поскольку они могут использовать эти привязки или поведения. Поэтому пользователь, изменяющий привязки и поведения по умолчанию, должен знать, что эти изменения могут повлиять на другие службы в иерархии.  
  
> [!NOTE]
> Службы, размещенные в службах IIS или WAS, используют в качестве базового адреса виртуальный каталог.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 В предыдущем примере конечная точка с базовым адресом, начинающимся с «http», использует привязку <xref:System.ServiceModel.BasicHttpBinding>. Конечная точка с базовым адресом, начинающимся с «net.tcp», использует привязку <xref:System.ServiceModel.NetTcpBinding>. Параметры можно переопределить в локальном файле App.config или Web.config.  
  
 Каждый элемент `protocolMappings` в разделе <> должен указывать схему и привязку. В обязательном порядке `bindingConfiguration` он может указать атрибут, определяющий связывающую конфигурацию в <`bindings`> разделе файла конфигурации. Если параметры `bindingConfiguration` не заданы, то используется анонимная конфигурация привязки нужного типа.  
  
 Поведение службы настраивается для конечных точек `behavior` по умолчанию с помощью анонимных разделов <> в разделах <`serviceBehaviors`>. Для настройки `behavior` поведения службы используются все элементы неназванных> <в <`serviceBehaviors`>. Например, следующий файл конфигурации позволяет публиковать метаданные всех служб в узле.  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 Поведение конечных точек настраивается `behavior` с помощью `serviceBehaviors` анонимных разделов> <в разделах <>.  
  
 В следующем примере приведен файл конфигурации, эквивалентный файлу, приведенному в начале данного раздела, с упрощенной моделью конфигурации.  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> Эта возможность относится только к конфигурации службы WCF, а не к конфигурации клиента. В большинстве случаев конфигурация клиента WCF создается с помощью средства, например svcutil.exe, или путем добавления ссылки на службу из Visual Studio. Если вы вручную настраиваете клиент WCF, вам \<нужно будет добавить элемент клиента> в конфигурацию и указать все конечные точки, которые вы хотите позвонить.  
  
## <a name="see-also"></a>См. также

- [Настройка служб с использованием файлов конфигурации](configuring-services-using-configuration-files.md)
- [Настройка привязок для служб](configuring-bindings-for-wcf-services.md)
- [Настройка привязок, предоставляемых системой](./feature-details/configuring-system-provided-bindings.md)
- [Настройка служб](configuring-services.md)
- [Настройка wCF-сервисов](configuring-services.md)
- [Настройка служб WCF в коде](configuring-wcf-services-in-code.md)
