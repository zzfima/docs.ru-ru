---
title: '&lt;assemblyIdentity&gt; элемент для &lt;среды выполнения&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5d985d1620b7dec324c0113bcd5652cede044950
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744971"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a>&lt;assemblyIdentity&gt; элемент для &lt;среды выполнения&gt;
Содержит идентификационные сведения о сборке.  
  
 \<configuration>  
\<Среда выполнения >  
\<assemblyBinding >  
\<dependentAssembly >  
\<assemblyIdentity >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Имя сборки|  
|`culture`|Необязательный атрибут.<br /><br /> Строка, указывающая язык и Страна или регион, сборки.|  
|`publicKeyToken`|Необязательный атрибут.<br /><br /> Шестнадцатеричное значение, указывающее строгое имя сборки.|  
|`processorArchitecture`|Необязательный атрибут.<br /><br /> Одно из значений «x86», «amd64», «msil» или «ia64», задающих архитектуру процессора для сборки, содержащей код для конкретного процессора. Значения не учитывают регистр. Если атрибуту назначено любое другое значение, вся `<assemblyIdentity>` элемент игнорируется. См. раздел <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>processorArchitecture атрибута  
  
|Значение|Описание|  
|-----------|-----------------|  
|`amd64`|Только для 64-разрядных процессоров AMD.|  
|`ia64`|Только для 64-разрядных процессоров Intel.|  
|`msil`|Нейтральный с точки зрения процессор и количество бит на слово|  
|`x86`|Для 32-разрядных процессоров Intel, либо машинный код или в среде Windows (WOW) на 64-разрядной платформе Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`dependentAssembly`|Инкапсулирует политику привязки и расположение каждой сборки. Используйте один `<dependentAssembly>` элемент для каждой сборки.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Каждый  **\<dependentAssembly >** элемент должен иметь один  **\<assemblyIdentity >** дочерний элемент.  
  
 Если `processorArchitecture` присутствует атрибут `<assemblyIdentity>` элемент применяется только к сборке с соответствующей архитектурой процессора. Если `processorArchitecture` атрибут не задан, `<assemblyIdentity>` элемент можно применить к сборке с любой архитектурой процессора.  
  
 В следующем примере показан файл конфигурации для двух сборок с тем же именем, предназначенных для двух различных архитектур процессоров и версий, не синхронизированных синхронизирован. При выполнении приложения на x86 платформы первый `<assemblyIdentity>` применяет элемента и другое обрабатывается. Если приложение выполняется на платформе, отличной от x86 или ia64, оба атрибута игнорируются.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Если файл конфигурации содержит `<assemblyIdentity>` элемента нет `processorArchitecture` атрибута и не содержит элемент, соответствующий платформе элемент без `processorArchitecture` используется атрибут.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для предоставления сведений о сборке.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
