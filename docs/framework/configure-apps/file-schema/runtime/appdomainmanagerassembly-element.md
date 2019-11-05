---
title: Элемент <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 7ba52cdf0102af05954509a11fa90e9b8a337876
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118321"
---
# <a name="appdomainmanagerassembly-element"></a>\<Аппдомаинманажерассембли > элемент
Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<аппдомаинманажерассембли >**  
  
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
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Заметки  
 Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и элемент [\<аппдомаинманажертипе >](appdomainmanagertype-element.md) . Если один из этих элементов не указан, другой игнорируется.  
  
 При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> создается, если указанная сборка не существует или если сборка не содержит тип, указанный в элементе [\<аппдомаинманажертипе >](appdomainmanagertype-element.md) . и процесс не запускается. Если сборка найдена, но сведения о версии не совпадают, создается <xref:System.IO.FileLoadException>.  
  
 При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения. Используйте свойства <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>, чтобы указать другой тип диспетчера домена приложения для нового домена приложения.  
  
 Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие. (Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, выдается <xref:System.TypeLoadException>.  
  
 Сведения о формате отображаемого имени сборки см. в описании свойства <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.  
  
 Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса является типом `MyMgr` в сборке `AdMgrExample`.  
  
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
- [\<Аппдомаинманажертипе > элемент](appdomainmanagertype-element.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Метод SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
