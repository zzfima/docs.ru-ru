---
title: '&lt;loadFromRemoteSources&gt; элемент'
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a8858059159edddb4456561719c572fb9268be7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509487"
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;loadFromRemoteSources&gt; элемент
Указывает, следует ли предоставлять полное доверие в .NET Framework 4 и более поздних версий сборки, загруженные из удаленных источников.
  
> [!NOTE]
>  Если вы перешли на этот раздел из-за сообщение об ошибке в списке ошибок Visual Studio проекта или ошибка сборки, см. в разделе [как: использовать сборку из Интернета в Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).  
  
 \<configuration>  
\<Среда выполнения >  
\<loadFromRemoteSources >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, следует ли предоставлять полного уровня доверия сборки, загруженной из удаленного источника.|  
  
## <a name="enabled-attribute"></a>атрибут Enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не предоставляйте полное доверие к приложениям из удаленных источников. Это значение по умолчанию.|  
|`true`|Предоставить полное доверие к приложениям из удаленных источников.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания

В .NET Framework 3.5 и более ранних версий Если загрузить сборку из удаленного расположения, код в сборке, выполняется в режиме частичного доверия с набором прав, который зависит от зоны, из которого загружается. Например если сборку загрузить с веб-сайта, он загружается в зоне Интернета и предоставлен набор разрешений Интернета. Другими словами он выполняет в песочнице Интернета.

Начиная с .NET Framework 4, политику разграничения доступа кода отключена и сборки загружаются в режиме полного доверия. Как правило, это предоставить полное доверие для сборки, загруженные с <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> метод, который ранее был изолированной. Чтобы избежать этого, по умолчанию отключена возможность запуска кода в сборки, загруженные из удаленного источника. По умолчанию, при попытке загрузить удаленную сборку <xref:System.IO.FileLoadException> с сообщением об исключении, как возникает следующее:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Для загрузки сборки и выполнения его кода, необходимо:

- Явным образом создать "песочницу" для сборки (см. в разделе [как: выполнение частично доверенного кода в изолированной среде](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Выполнение кода сборки с полным доверием. Это можно сделать, настроив `<loadFromRemoteSources>` элемент. Он позволяет указать, что сборки, работающих в режиме частичного доверия в более ранних версиях платформы .NET Framework теперь выполняются в режиме полного доверия в .NET Framework 4 и более поздних версий.

> [!IMPORTANT]
> Если сборки не должно выполняться в режиме полного доверия, не устанавливайте этот элемент конфигурации. Вместо этого создайте изолированной <xref:System.AppDomain> для загрузки сборки.

`enabled` Для атрибута `<loadFromRemoteSources>` элемент действует, только когда отключено управление доступом для кода (CAS). По умолчанию политика CAS отключена в .NET Framework 4 и более поздних версий. Если задать `enabled` для `true`, удаленного сборкам предоставляется полное доверие.

Если `enabled` равно `true`, <xref:System.IO.FileLoadException> возникает исключение в одном из следующих условий:

- Поведение "песочницы" текущего домена отличается от его поведение в .NET Framework 3.5. Для этого политики разграничения доступа кода отключена и текущий домен не изолирована.

- Загружаемая сборка не из `MyComputer` зоны.

Установка `<loadFromRemoteSources>` элемент `true` предотвращает это исключение вызывается. Он позволяет указать, что вы не полагаетесь на среда CLR для "песочницы" загруженных сборок в, и что они могут быть могут выполняться в режиме полного доверия.

## <a name="notes"></a>Примечания

- В .NET Framework 4.5 и более поздних версий сборки в общих папках локальной сети выполняются в режиме полного доверия по умолчанию. необходимо включить `<loadFromRemoteSources>` элемент.

- Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере. Это обозначение можно изменить, изменив его свойства файла, или воспользоваться `<loadFromRemoteSources>` элемент для предоставления сборке полное доверие. Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.

- Может появиться <xref:System.IO.FileLoadException> в приложении, которое выполняется в приложении Windows Virtual PC. Это может произойти при попытке загрузить файл из связанных папок на компьютера для размещения. Она также может возникать при попытке загрузить файл из папки, связанной через [служб удаленных рабочих столов](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services Client). Чтобы избежать этого исключения, задайте `enabled` для `true`.

## <a name="configuration-file"></a>файл конфигурации

Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста. Дополнительные сведения см. в статье [дополнительные неявного использования политики CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) в блоге .NET Security.  

## <a name="example"></a>Пример

В следующем примере показано, как предоставить полное доверие для сборок, загруженных из удаленных источников.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>См. также

[Более неявного использования политики CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)  
[Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
[Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
[Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
