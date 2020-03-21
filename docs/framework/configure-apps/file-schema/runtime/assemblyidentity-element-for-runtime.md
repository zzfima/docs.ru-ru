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
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154313"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<assemblyIdentity> \<Элемент для> времени выполнения
Содержит идентифицирующую информацию о сборке.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<сборкаОбязательная>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<зависимаясборка>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сборкаIdentityличная>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Название сборки|  
|`culture`|Необязательный атрибут.<br /><br /> Строка, опоменавававательства языка и страны/региона собрания.|  
|`publicKeyToken`|Необязательный атрибут.<br /><br /> Гексадецимическое значение, которое определяет сильное название сборки.|  
|`processorArchitecture`|Необязательный атрибут.<br /><br /> Одно из значений "x86", "amd64", "msil" или "ia64", определяющее архитектуру процессора для сборки, содержащей код для процессора. Значения не чувствительны к случаям. Если атрибуту присваивается `<assemblyIdentity>` какое-либо другое значение, весь элемент игнорируется. См. раздел <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>processorArchitecture Атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`amd64`|AMD x86-64 только архитектура.|  
|`ia64`|Только архитектура Intel Itanium.|  
|`msil`|Код нейтрален по отношению к процессору и разрядности слова.|  
|`x86`|32-разрядный процессор x86, как родной, так и в среде Windows на Windows (WOW) на 64-битной платформе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`dependentAssembly`|Инкапсулирует политику привязки и расположение каждой сборки. Используйте `<dependentAssembly>` один элемент для каждой сборки.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 Каждый ** \<зависимый элементсборки>** должен иметь одну ** \<сборкуIdentity>** элемента ребенка.  
  
 При `processorArchitecture` наличии атрибута `<assemblyIdentity>` элемент применяется только к сборке с соответствующей архитектурой процессора. Если `processorArchitecture` атрибут не присутствует, `<assemblyIdentity>` элемент может применяться к сборке с любой архитектурой процессора.  
  
 В следующем примере показан файл конфигурации для двух сборок с одинаковым именем, ориентированный на две разные две архитектуры процессора и версии которых не были синхронизированы. Когда приложение выполняется на платформе x86, первый `<assemblyIdentity>` элемент применяется, а другой игнорируется. Если приложение выполняется на платформе, кроме x86 или ia64, оба игнорируются.  
  
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
  
 Если файл конфигурации `<assemblyIdentity>` содержит `processorArchitecture` элемент без атрибута и не содержит элемента, `processorArchitecture` который соответствует платформе, используется элемент без атрибута.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как предоставить информацию о сборке.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [Перенаправление версий сборки](../../redirect-assembly-versions.md)
