---
title: элемент конфигурации <supportedRuntime> — .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 5e7fc5f81468ff7c4eba8145ee42a4c7cf8bc0b8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697519"
---
# <a name="supportedruntime-element"></a>\<supportedRuntime > элемент

Указывает, какая версия среды CLR и, при необходимости, .NET Framework версия, поддерживаемая приложением.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<запуска >](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<supportedRuntime >**  

## <a name="syntax"></a>Синтаксис

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|**version**|Необязательный атрибут.<br /><br /> Строковое значение, задающее версию среды CLR, которая поддерживается данным приложением. Допустимые значения атрибута `version` см. в разделе [значения "версия среды выполнения"](#version) . **Примечание.**  С помощью .NET Framework 3,5 значение "*версия среды выполнения*" принимает форму " *основной*". *дополнительный номер*. *Сборка*. Начиная с .NET Framework 4, требуются только основной и дополнительный номера версии (т. е. "v 4.0" вместо "v 4.0.30319"). Рекомендуется использовать более короткие строки.|
|**sku**|Необязательный атрибут.<br /><br /> Строковое значение, которое указывает единицу складского хранения (SKU), которая, в свою очередь, указывает выпуск .NET Framework, поддерживаемый этим приложением.<br /><br /> Начиная с .NET Framework 4.0, рекомендуется использовать атрибут `sku`.  Если он присутствует, он указывает целевую версию .NET Framework приложения.<br /><br /> Допустимые значения атрибута SKU см. в разделе [значения номера SKU](#sku) .|

## <a name="remarks"></a>Примечания

Если элемент **\<supportedRuntime >** отсутствует в файле конфигурации приложения, используется версия среды выполнения, используемая для построения приложения.

**\<SupportedRuntime>** элемент должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии среды выполнения. Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать элемент [\<requiredRuntime >](../startup/requiredruntime-element.md) .

> [!NOTE]
> При использовании функции [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации необходимо использовать элемент `<requiredRuntime>` для всех версий среды выполнения. Элемент `<supportedRuntime>` игнорируется при использовании [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
Для приложений, поддерживающих версии среды выполнения от .NET Framework 1.1 до 3.5, при поддержке нескольких версий среды выполнения первый элемент должен задавать наиболее предпочтительную версию среды, а последний — наименее предпочтительную. Для приложений, поддерживающих .NET Framework 4,0 или более поздних версий, атрибут `version` указывает версию среды CLR, которая является общей для .NET Framework 4 и более поздних версий, а атрибут `sku` указывает на одну версию .NET Framework, для которой предназначено приложение. 

Если элемент **\<supportedRuntime >** с атрибутом `sku` содержится в файле конфигурации, а версия установленного .NET Framework меньше, чем указанная поддерживаемая версия, приложение не запускается, а вместо этого отображается сообщение с запросом на установку поддерживаемой версии. В противном случае приложение пытается запуститься в любой установленной версии, но может вести себя неожиданно, если она не полностью совместима с этой версией. (Сведения о различиях в совместимости версий .NET Framework см. [в разделе Совместимость приложений в .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Поэтому рекомендуется включить этот элемент в файл конфигурации приложения для упрощения диагностики ошибок. (Файл конфигурации, автоматически созданный Visual Studio при создании нового проекта, уже содержит его.)
  
> [!NOTE]
> Если ваше приложение использует пути активации прежних версий, например [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и вы хотите, чтобы эти пути активировали версию 4 среды CLR вместо более ранней версии или если приложение создано с .NET Framework 4, но имеет зависимость от сборки в смешанном режиме, построенной с использованием более ранней версии .NET Framework, не достаточно указать .NET Framework 4 в списке поддерживаемых сред выполнения. Кроме того, в [элементе\<startup >](../startup/startup-element.md) в файле конфигурации необходимо задать для атрибута `useLegacyV2RuntimeActivationPolicy` значение `true`. Однако присвоение этому атрибуту значения `true` означает, что все компоненты, созданные с помощью более ранних версий .NET Framework, выполняются с использованием .NET Framework 4 вместо сред выполнения, в которых они были созданы.

Приложения рекомендуется тестировать со всеми версиями .NET Framework, в которых они могут работать.

<a name="version"></a> 
## <a name="runtime-version-values"></a>Значения "runtime version"
Атрибут `runtime` указывает версию среды CLR, необходимую для данного приложения. Обратите внимание, что все версии .NET Framework v4. x указывают `v4.0` CLR. В следующей таблице приведены допустимые значения для значения *Version среды выполнения* атрибута `version`.

|Версия платформы .NET Framework|атрибут `version`|
|----------------------------|-------------------------|
|1,0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3,0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0 — 4.8|"v4.0"|

## <a name="sku"></a>значения "ИД SKU"

Атрибут `sku` использует моникер целевой платформы (TFM) для указания версии .NET Framework, которая предназначена для приложения и требует выполнения. В следующей таблице перечислены допустимые значения, поддерживаемые атрибутом `sku`, начиная с .NET Framework 4.

|Версия платформы .NET Framework|атрибут `sku`|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, клиентский профиль|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, обновление платформы 1|". NETFramework, Version = v 4.0.1 "|
|4.0, клиентский профиль, обновление 1|". NETFramework, Version = v 4.0.1, Profile = Client|
|4.0, обновление платформы 2|". NETFramework, Version = v 4.0.2 "|
|4.0, клиентский профиль, обновление 2|". NETFramework, Version = v 4.0.2, Profile = Client|
|4.0, обновление платформы 3|". NETFramework, Version = v 4.0.3 "|
|4.0, клиентский профиль, обновление 3|". NETFramework, Version = v 4.0.3, Profile = Client|
|4,5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework, Version = v 4.6.2 "|
|4.7|". NETFramework, Version = v 4.7|
|4.7.1|". NETFramework, Version = v 4.7.1 "|
|4.7.2|". NETFramework, Version = v 4.7.2 "|
|4.8|". NETFramework, Version = v 4.8 "|

## <a name="example"></a>Пример

В следующем примере показано задание в файле конфигурации поддерживаемых версий среды выполнения. Файл конфигурации указывает, что приложение предназначено для .NET Framework 4,7.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент может использоваться в файле конфигурации приложения.

## <a name="see-also"></a>См. также:

- [Схема параметров запуска](../startup/index.md)
- [Схема файла конфигурации](../index.md)
- [Внутрипроцессное параллельное выполнение](../../../deployment/in-process-side-by-side-execution.md)
