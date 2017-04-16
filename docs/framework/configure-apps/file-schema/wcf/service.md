---
title: "&lt;service&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# &lt;service&gt;
Элемент `service` содержит параметры для службы Windows Communication Foundation \(WCF\).  Он также содержит конечные точки, предоставляющие доступ к службе.  
  
## Синтаксис  
  
```  
  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|behaviorConfiguration|Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы.  Имя поведения должно входить в область действия в точке определения службы.  Значение по умолчанию \- пустая строка.|  
|имя|Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается.  Этот параметр должен иметь значение допустимого типа.  Формат должен быть `Namespace.Class.`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<конечная точка\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.|  
|[\<хост\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Задает узел данного экземпляра службы.  Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<службы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Корневой элемент всех элементов конфигурации WCF.|  
  
## Заметки  
 Службы задаются в разделе `services` файла конфигурации.  Сборка может содержать любое число служб.  Для каждой службы используется собственный раздел конфигурации `service`.  В этом разделе определяются контракт, поведение и конечные точки конкретной службы.  
  
 Элемент `behaviorConfiguration` также является необязательным.  Он указывает поведение, используемое службой.  Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.  
  
 Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки.  Все привязки в файле конфигурации должны быть определены в области файла.  Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`.  Атрибут `name` описывает раздел, в котором определена привязка.  Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется.  В разделе привязки может определяться несколько конфигураций.  
  
## Пример  
 Ниже приведен пример конфигурации службы.  
  
```  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceElement>   
 [Настройка служб](../../../../../docs/framework/wcf/configuring-services.md)