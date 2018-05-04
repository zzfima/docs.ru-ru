---
title: '&lt;appDomainManagerType&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fb771d58a99e42ad53a465008e8848cff0a87fd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltappdomainmanagertypegt-element"></a>&lt;appDomainManagerType&gt; элемент
Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.  
  
 \<configuration>  
\<Среда выполнения >  
\<appDomainManagerType >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`value`|Обязательный атрибут. Задает имя типа, включая пространство имен, которая служит диспетчер домена приложения для домена приложения по умолчанию в процессе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы задать тип диспетчера домена приложения, необходимо задать как этот элемент и [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) элемента. Если один из этих элементов не задан, другой игнорируется.  
  
 При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> создается, если указанный тип не существует в сборке, которая определяется [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) элементу; и завершилось неудачно для Начало.  
  
 Если указать тип диспетчера домена приложения для домена приложения по умолчанию, другие домены приложений, созданные на основе домена приложения по умолчанию наследуют тип диспетчера домена приложения. Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> свойства, чтобы указать тип диспетчера домена приложения в новом домене приложения.  
  
 Определяющее тип диспетчера домена приложения требует полного доверия приложения. (Например, приложения, работающего на рабочем столе имеет полное доверие). Если приложение не имеет полного доверия <xref:System.TypeLoadException> возникает исключение.  
  
 Формат типа и пространство имен имеет тот же формат, используемый для <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства.  
  
 Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версий.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса `MyMgr` введите `AdMgrExample` сборки.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [\<appDomainManagerAssembly > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Метод SetAppDomainManagerType](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
