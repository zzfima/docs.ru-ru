---
title: "&lt;bindingElementExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;bindingElementExtensions&gt;
В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.  Элемент пользовательской привязки можно добавить в эту коллекцию, используя ключевое слово `add`, присвоив атрибуту `type` элемента значение, соответствующее расширению элемента привязки, и указав в атрибуте `name` пользовательский элемент привязки.  
  
 Расширения привязки позволяют пользователю создавать свои собственные элементы привязки и задействовать их как часть пользовательских привязок.  Ну уровне программирования расширение привязки представляет собой тип, реализующий абстрактный класс <xref:System.ServiceModel.Channels.BindingElement>.  В файле конфигурации раздел `bindingElementExtensions` используется для определения элемента расширения.  
  
 В следующем примере элемент `add` и атрибут `name` используются для добавления расширения привязки в раздел `bindingElementExtensions` файла конфигурации.  
  
```  
<system.serviceModel>  
    <extensions>  
        <bindingElementExtensions>  
           <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingElementExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Чтобы добавить в элемент возможность настройки, пользователю следует записать и зарегистрировать элемент `bindingElementExtensionSection`.  Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.  
  
 После определения элемента и типа его конфигурации расширение можно использовать как часть пользовательской привязки \(см. следующий пример\).  
  
```  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)