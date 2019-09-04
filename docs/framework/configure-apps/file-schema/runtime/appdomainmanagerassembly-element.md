---
title: Элемент <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 083e3ba21dcd196eacfe3d9fd649c211da9dc125
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252849"
---
# <a name="appdomainmanagerassembly-element"></a>\<Элемент > Аппдомаинманажерассембли
Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Аппдомаинманажерассембли >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`value`|Обязательный атрибут. Указывает отображаемое имя сборки, предоставляющей Диспетчер доменов приложений для домена приложения по умолчанию в процессе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и [ \<элемент > аппдомаинманажертипе](appdomainmanagertype-element.md) . Если один из этих элементов не указан, другой игнорируется.  
  
 Когда загружается домен приложения по умолчанию, создается исключение, <xref:System.TypeLoadException> если указанная сборка не существует или сборка не содержит тип, указанный [ \<элементом аппдомаинманажертипе >](appdomainmanagertype-element.md) ; и процесс не может запустить. Если сборка найдена, но сведения о версии не совпадают, <xref:System.IO.FileLoadException> создается исключение.  
  
 При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения. Используйте свойства <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> и, чтобы указать другой тип диспетчера домена приложения для нового домена приложения. <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
  
 Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие. (Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, <xref:System.TypeLoadException> создается исключение.  
  
 Сведения о формате отображаемого имени сборки см. в <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> описании свойства.  
  
 Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса — это `MyMgr` тип `AdMgrExample` в сборке.  
  
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

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<Элемент > Аппдомаинманажертипе](appdomainmanagertype-element.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Метод SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
