---
title: Элемент <assemblyIdentity> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: 815e1c26a328d986f91992a1e67e438a563ffea6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663889"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<элемент assemblyIdentity > для \<> среды выполнения
Содержит идентифицирующие сведения о сборке.  
  
 \<configuration>  
\<> среды выполнения  
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
|`processorArchitecture`|Необязательный атрибут.<br /><br /> Одно из значений "x86", "amd64", "MSIL" или "ia64", определяющее архитектуру процессора для сборки, содержащей код, зависящий от процессора. В значениях регистр не учитывается. Если атрибуту присвоено любое другое значение, весь `<assemblyIdentity>` элемент игнорируется. См. раздел <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>Атрибут processorArchitecture  
  
|Значение|Описание|  
|-----------|-----------------|  
|`amd64`|Только архитектура AMD x86-64.|  
|`ia64`|Только архитектура Intel Itanium.|  
|`msil`|Не зависит от процессора и разрядов на каждое слово.|  
|`x86`|32-разрядный процессор x86, либо собственный, либо в среде Windows on Windows (WOW) на 64-разрядной платформе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`dependentAssembly`|Инкапсулирует политику привязки и расположение каждой сборки. Для каждой `<dependentAssembly>` сборки используется один элемент.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 **Каждый\<элемент dependentAssembly >** должен иметь один  **\<** дочерний элемент assemblyIdentity >.  
  
 Если атрибут имеется `<assemblyIdentity>` , элемент применяется только к сборке с соответствующей архитектурой процессора. `processorArchitecture` Если атрибут отсутствует `<assemblyIdentity>` , элемент может применяться к сборке с любой архитектурой процессора. `processorArchitecture`  
  
 В следующем примере показан файл конфигурации для двух сборок с одинаковым именем, предназначенных для двух разных архитектур процессора, чьи версии не поддерживали синхронизацию. При выполнении приложения на платформе x86 первый `<assemblyIdentity>` элемент применяется, а другой игнорируется. Если приложение выполняется на платформе, отличной от x86 или ia64, то оба они игнорируются.  
  
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
  
 Если файл конфигурации содержит `<assemblyIdentity>` элемент `processorArchitecture` без атрибута и не содержит элемент, соответствующий платформе `processorArchitecture` , то используется элемент без атрибута.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как предоставить сведения о сборке.  
  
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

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Перенаправление версий сборки](../../redirect-assembly-versions.md)
