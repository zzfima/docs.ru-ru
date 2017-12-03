---
title: '&lt;compositeDuplex&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 292067daacc9319c144e9d0f2da9f27ca2fcf5b1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcompositeduplexgt"></a>&lt;compositeDuplex&gt;
Определяет элемент привязки, который используется, когда клиенту необходимо предоставить службе конечную точку для отправки сообщений обратно клиенту.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<compositeDuplex >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|clientBaseAddress|Универсальный код ресурса (URI), который задает адрес обратного канала при работе в дуплексном режиме. Служба использует данный адрес для осуществления контакта и создания подключения к клиенту.<br /><br /> Если этот атрибут не установлен, адрес по умолчанию «`full qualified name+default port\TemporaryIndigoAddress\guid`» создается. Значение по умолчанию — `null`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Данный элемент конфигурации используется с теми типами транспорта, которые не имеют встроенной поддержки дуплексной связи, например HTTP. Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.  
  
 Для осуществления контакта и установления подключения клиент должен предоставить службе адрес. Этот адрес клиента предоставляется атрибутом `clientBaseAddress`. Обратите внимание, что Windows Communication Foundation (WCF) автоматически создает атрибут ClientBaseAddress в том случае, если он не был явно задан пользователем.  
  
## <a name="example"></a>Пример  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>  
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
