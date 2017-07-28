---
title: "Элемент &lt;supportedRuntime&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<supportedRuntime> - элемент"
  - "supportedRuntime - элемент"
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
caps.latest.revision: 33
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 28
---
# Элемент &lt;supportedRuntime&gt;
Указывает, какие версии среды CLR поддерживает приложение. Этот элемент должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии .NET Framework.  
  
 [\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
  
 **\<supportedRuntime\>**  
  
## Синтаксис  
  
```  
  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**version**|Необязательный атрибут.<br /><br /> Строковое значение, задающее версию среды CLR, которая поддерживается данным приложением. Допустимые значения атрибута `version` см. в разделе [Значения "runtime version"](#version). **Note:**  В .NET Framework 3.5 значение версии *runtime version* принимает форму *основной номер*.*дополнительный номер*.*сборка*. Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], требуются только основной и дополнительный номера версии \(то есть "v4.0" вместо "v4.0.30319"\). Рекомендуется использовать более короткие строки.|  
|**sku**|Необязательный атрибут.<br /><br /> Строковое значение, которое указывает единицу складского хранения \(SKU\), которая, в свою очередь, указывает выпуск .NET Framework, поддерживаемый этим приложением.<br /><br /> Начиная с .NET Framework 4.0, рекомендуется использовать атрибут `sku`.  Если он присутствует, он указывает целевую версию .NET Framework приложения.<br /><br /> Допустимые значения атрибута SKU см. в разделе [Значения "sku id"](#sku).|  
  
## Заметки  
 Если элемент **\<supportedRuntime\>** отсутствует в файле конфигурации приложения, используется версия среды выполнения, которая применялась для сборки приложения.  
  
 Элемент **\<supportedRuntime\>** должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии среды выполнения. Приложения, собранные для поддержки только версии 1.0 среды выполнения, должны использовать элемент [\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md).  
  
> [!NOTE]
>  При применении функции [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для задания файла конфигурации необходимо использовать элемент `<requiredRuntime>` для всех версий среды выполнения. При использовании функции [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) элемент `<supportedRuntime>` игнорируется.  
  
 Для приложений, поддерживающих версии среды выполнения от .NET Framework 1.1 до 3.5, при поддержке нескольких версий среды выполнения первый элемент должен задавать наиболее предпочтительную версию среды, а последний — наименее предпочтительную. Для приложений, поддерживающих .NET Framework 4.0 или более поздних версий, атрибут `version` указывает версию CLR, общую для .NET Framework 4 и более поздних версий, а атрибут `sku` указывает одну целевую версию .NET Framework приложения.  
  
> [!NOTE]
>  Если приложение использует устаревшие пути активации, например [функцию CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), и эти пути требуются для активации версии 4 среды CLR вместо более ранней версии, или если приложение собрано с применением [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], но зависит от сборки смешанного режима, выполненной с использованием более ранней версии .NET Framework, то в списке поддерживаемых сред недостаточно указать [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]. Кроме того, в элементе [\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) файла конфигурации атрибуту `useLegacyV2RuntimeActivationPolicy` необходимо присвоить значение `true`. Однако при установке для этого атрибута значения `true` все компоненты, собранные с более ранними версиями .NET Framework, будут работать с использованием [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], а не сред выполнения, с которыми они были собраны.  
  
 Приложения рекомендуется тестировать со всеми версиями .NET Framework, в которых они могут работать.  
  
<a name="version"></a>   
## Значения "runtime version"  
 В следующей таблице перечислены допустимые значения для *runtime version* атрибута `version`.  
  
|Версия платформы .NET Framework|Атрибут `version`|  
|-------------------------------------|-----------------------|  
|1,0|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0|"v4.0"|  
|4.5|"v4.0"|  
|4.5.1|"v4.0"|  
|4.5.2|"v4.0"|  
|4.6|"v4.0"|  
|4.6.1|"v4.0"|  
  
<a name="sku"></a>   
## Значения "sku id"  
 В следующей таблице перечислены версии .NET Framework, начиная с .NET Framework 4, которые поддерживаются атрибутом `sku`.  Обратите внимание, что атрибут `sku`, начиная с .NET Framework 4, указывает целевую версию .NET Framework приложения.  
  
|Версия платформы .NET Framework|Атрибут `sku`|  
|-------------------------------------|-------------------|  
|4.0|".NETFramework,Version\=v4.0"|  
|4.0, клиентский профиль|".NETFramework,Version\=v4.0,Profile\=Client"|  
|4.0, обновление платформы 1|.NETFramework,Version\=v4.0.1|  
|4.0, клиентский профиль, обновление 1|.NETFramework,Version\=v4.0.1,Profile\=Client|  
|4.0, обновление платформы 2|.NETFramework,Version\=v4.0.2|  
|4.0, клиентский профиль, обновление 2|.NETFramework,Version\=v4.0.2,Profile\=Client|  
|4.0, обновление платформы 3|.NETFramework,Version\=v4.0.3|  
|4.0, клиентский профиль, обновление 3|.NETFramework,Version\=v4.0.3,Profile\=Client|  
|4.5|".NETFramework,Version\=v4.5"|  
|4.5.1|".NETFramework,Version\=v4.5.1"|  
|4.5.2|".NETFramework,Version\=v4.5.2"|  
|4.6|".NETFramework,Version\=v4.6"|  
|4.6.1|".NETFramework,Version\=v4.6.1"|  
  
 В следующей таблице показано, в каких установленных версиях .NET Framework 4 будет работать приложение при разных значениях атрибута `sku`, когда атрибут `version` имеет значение v4.0, а в атрибуте `sku` указаны версия .NET Framework 4 или одно из обновлений платформы \(PU\).  
  
|Значение атрибута `sku`|4.0 клиентская|4.0 полная|4.0 клиентская \+ обновления платформы 1|4.0 полная \+ обновления платформы 1|4.0 клиентская \+ обновление платформы 2|4.0 полная \+ обновление платформы 2|4.0 клиентская \+ обновление платформы 3|4.0 полная \+ обновление платформы 3|4.5 и более поздние версии|  
|-----------------------------|--------------------|----------------|----------------------------------------------|------------------------------------------|----------------------------------------------|------------------------------------------|----------------------------------------------|------------------------------------------|--------------------------------|  
|.NETFramework,Version\=v4.0,Profile\=Client|Да|Да|Да|Да|Да|Да|Да|Да|Да|  
|.NETFramework,Version\=v4.0||Да||Да||Да||Да|Да|  
|.NETFramework,Version\=v4.0.1,Profile\=Client|||Да|Да|Да|Да|Да|Да|Да|  
|.NETFramework,Version\=v4.0.1||||Да||Да||Да|Да|  
|.NETFramework,Version\=v4.0.2,Profile\=Client|||||Да|Да|Да|Да|Да|  
|.NETFramework,Version\=v4.0.2||||||Да||Да|Да|  
|.NETFramework,Version\=v4.0.3,Profile\=Client|||||||Да|Да|Да|  
|.NETFramework,Version\=v4.0.3||||||||Да|Да|  
  
## Пример  
 В следующем примере показано задание в файле конфигурации поддерживаемых версий среды выполнения. В файле конфигурации указано, что приложение предназначено для .NET Framework 4.6.  
  
```xml  
  
<configuration> <startup> <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" /> </startup> </configuration>  
  
```  
  
## Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения.  
  
## См. также  
 [Схема параметров запуска](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Указание используемой версии среды выполнения](http://msdn.microsoft.com/ru-ru/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Внутрипроцессное параллельное выполнение](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)