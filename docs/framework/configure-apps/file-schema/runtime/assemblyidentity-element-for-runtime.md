---
title: <assemblyIdentity> Элемент для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: d5766b76f18dce441cb260887a753dcf64642a6f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098706"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<assemblyIdentity > элемент для \<среды выполнения >
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
|`culture`|Необязательный атрибут.<br /><br /> Строка, указывающая язык и страну или регион сборки.|  
|`publicKeyToken`|Необязательный атрибут.<br /><br /> Шестнадцатеричное значение, указывающее строгое имя сборки.|  
|`processorArchitecture`|Необязательный атрибут.<br /><br /> Одно из значений «x86», «amd64», «msil» или «ia64», указав архитектуру процессора для сборки, содержащей код для конкретного процессора. Значения не учитывают регистр. Если атрибуту назначено любое другое значение, весь `<assemblyIdentity>` элемент игнорируется. См. раздел <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>processorArchitecture атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`amd64`|AMD x86 64 только для архитектуры.|  
|`ia64`|Только архитектуру Intel Itanium.|  
|`msil`|Нейтральный по отношению к процессору и количество бит на слово.|  
|`x86`|32-разрядный x86 процессора, собственным или в Windows в среде Windows (WOW) на 64-разрядной платформе.|  
  
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
  
 Если `processorArchitecture` присутствует атрибут, `<assemblyIdentity>` элемент применяется только к сборке с соответствующей архитектурой процессора. Если `processorArchitecture` атрибут не задан, `<assemblyIdentity>` элемент можно применить к сборке с любой архитектурой процессора.  
  
 В следующем примере показан файл конфигурации для двух сборок с тем же именем, предназначенных для двух различных архитектур процессоров и версий, не синхронизированных синхронизацию. При выполнении приложения на x86 платформы первый `<assemblyIdentity>` элемент применяется, и другое обрабатывается. Если приложение выполняется на платформе, отличной от x86 или ia64, оба атрибута игнорируются.  
  
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
  
 Если файл конфигурации содержит `<assemblyIdentity>` элемент, не имеющий `processorArchitecture` атрибут и не содержит элемент, соответствующий платформе, к элементу без `processorArchitecture` используется атрибут.  
  
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

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
