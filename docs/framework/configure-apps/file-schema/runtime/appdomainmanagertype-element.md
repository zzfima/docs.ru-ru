---
title: Элемент <appDomainManagerType>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ffb297cc38f20917e720b216607e9ccfc966866
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252830"
---
# <a name="appdomainmanagertype-element"></a>\<Элемент > Аппдомаинманажертипе
Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Аппдомаинманажертипе >**  
  
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
|`value`|Обязательный атрибут. Указывает имя типа, включая пространство имен, которое служит диспетчером доменов приложений для домена приложения по умолчанию в процессе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и [ \<элемент > аппдомаинманажерассембли](appdomainmanagerassembly-element.md) . Если один из этих элементов не указан, другой игнорируется.  
  
 Когда загружается домен приложения по умолчанию, <xref:System.TypeLoadException> вызывается исключение, если указанный тип не существует в сборке, заданной [ \<элементом > аппдомаинманажерассембли](appdomainmanagerassembly-element.md) , и процесс не запускается.  
  
 При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения. Используйте свойства <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> и, чтобы указать другой тип диспетчера домена приложения для нового домена приложения. <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
  
 Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие. (Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, <xref:System.TypeLoadException> создается исключение.  
  
 Формат типа и пространства имен совпадает с форматом, используемым для <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства.  
  
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
- [\<Элемент > Аппдомаинманажерассембли](appdomainmanagerassembly-element.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Метод SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
