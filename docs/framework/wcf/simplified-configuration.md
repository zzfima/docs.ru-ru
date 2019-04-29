---
title: Упрощенная конфигурация
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 13cf8bd46ef3aabb011cb2ddd207963235468662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967899"
---
# <a name="simplified-configuration"></a>Упрощенная конфигурация
Настройка служб Windows Communication Foundation (WCF) может оказаться сложной задачей. Разных параметров много, и не всегда легко понять, какие настройки необходимы. Хотя файлы конфигурации и увеличивают гибкость служб WCF, они также являются источником многих трудно обнаруживаемых проблем. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] устраняет эти проблемы, предоставляя способ уменьшить размер и упростить конфигурацию службы.  
  
## <a name="simplified-configuration"></a>Упрощенная конфигурация  
 В файлах конфигурации службы WCF <`system.serviceModel`> содержит раздел <`service`> для каждой размещенной службы. <`service`> Элемент содержит коллекцию элементов <`endpoint`> элементы, которые определяют конечные точки, открытые для каждой службы и по желанию набор поведений службы. <`endpoint`> Элементы указывают адрес, привязку и контракт, открытые в конечной точке и при необходимости конфигурацию привязки и поведения конечной точки. <`system.serviceModel`> Раздел также содержит <`behaviors`> элемент, позволяющий указать поведение служб или конечной точки. В следующем примере показан <`system.serviceModel`> раздел файла конфигурации.  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] делает Настройка службы WCF проще счет отмены требования для <`service`> элемента. Если вы не добавите <`service`> раздел или добавить конечные точки в <`service`> раздел и служба не задает программно конечных точек, то набор конечных точек по умолчанию автоматически добавляются к службе, по одному для каждого базовый адрес службы и на каждый контракт, используемый службой. В каждой из этих конечных точек адрес конечной точки соответствует базовому адресу, привязка определяется схемой базового адреса, а контракт - службой. Если не нужно задавать конечные точки или поведения служб или изменять какие-либо параметры привязки, то указывать файл конфигурации служб не нужно вообще. Если служба реализует два контракта, а на узле включен транспорт по протоколам HTTP и TCP, то узел службы создаст четыре точки по умолчанию: по одной на каждый контракт для каждого транспорта. Чтобы создать по умолчанию конечные точки, узел службы должен знать, какие привязки использовать. Эти параметры указываются в <`protocolMappings`> внутри раздела <`system.serviceModel`> раздела. <`protocolMappings`> Раздел содержит список схем транспортных протокола распределенных по типам привязки. Узел службы использует переданные ему базовые адреса, чтобы определить, какую привязку использовать. В следующем примере используется <`protocolMappings`> элемента.  
  
> [!WARNING]
>  Изменение элементов конфигурации по умолчанию, например привязок или поведений, может повлиять на службы, определенные на нижних уровнях иерархии конфигурации, поскольку они могут использовать эти привязки или поведения. Поэтому пользователь, изменяющий привязки и поведения по умолчанию, должен знать, что эти изменения могут повлиять на другие службы в иерархии.  
  
> [!NOTE]
>  Службы, размещенные в службах IIS или WAS, используют в качестве базового адреса виртуальный каталог.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 В предыдущем примере конечная точка с базовым адресом, начинающимся с «http», использует привязку <xref:System.ServiceModel.BasicHttpBinding>. Конечная точка с базовым адресом, начинающимся с «net.tcp», использует привязку <xref:System.ServiceModel.NetTcpBinding>. Параметры можно переопределить в локальном файле App.config или Web.config.  
  
 Каждый элемент внутри <`protocolMappings`> раздел должен задавать схему и привязку. Кроме того, можно указать `bindingConfiguration` атрибут, задающий конфигурацию привязки внутри <`bindings`> раздел файла конфигурации. Если параметры `bindingConfiguration` не заданы, то используется анонимная конфигурация привязки нужного типа.  
  
 Поведения службы настроены для конечных точек по умолчанию при помощи анонимных <`behavior`> в разделах <`serviceBehaviors`> разделах. Каждый неименованный <`behavior`> элементов <`serviceBehaviors`> используются для настройки поведений служб. Например, следующий файл конфигурации позволяет публиковать метаданные всех служб в узле.  
  
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
  
 Поведения конечных точек настроены при помощи анонимных <`behavior`> в разделах <`serviceBehaviors`> разделах.  
  
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
>  Эта возможность относится только к конфигурации службы WCF, а не к конфигурации клиента. В большинстве случаев конфигурация клиента WCF создается с помощью средства, например svcutil.exe, или путем добавления ссылки на службу из Visual Studio. Если пользователь вручную настраивает клиент WCF необходимо добавить \<клиента > элемент в конфигурацию и указать все конечные точки, которые должны вызываться.  
  
## <a name="see-also"></a>См. также

- [Настройка служб с использованием файлов конфигурации](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [Настройка привязок для служб](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Настройка привязок, предоставляемых системой](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Настройка служб](../../../docs/framework/wcf/configuring-services.md)
- [Настройка служб WCF](configuring-services.md)
- [Настройка служб WCF в коде](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
