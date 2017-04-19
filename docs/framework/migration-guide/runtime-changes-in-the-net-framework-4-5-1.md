---
title: "Изменения среды выполнения в .NET Framework 4.5.1 | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- runtime changes
- .NET Framework 4.5.1
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e4903c2f25354005f95b3ed8f9728cfe8a0a92e
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-451"></a>Изменения среды выполнения в .NET Framework 4.5.1
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, разработанные для [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] или версии 4.5, но выполняющиеся в версии 4.51. Они включают изменения в следующих областях.  
  
-   [Ядро](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
 Столбец "Scope" в следующих таблицах определяет важность каждого изменения.  
  
-   Основное. Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода. Обратите внимание, что ни одно из изменений среды выполнения не попадает в эту категорию.  
  
-   Незначительное. Изменение влияет на небольшое количество приложений или требует незначительного изменения кода.  
  
-   Пограничное. Изменение влияет на приложения в исключительных ситуациях.  
  
-   Прозрачное. Изменение не оказывает особого влияния на разработчика или пользователя приложения. При этом вносить изменения в приложения не требуется.  
  
<a name="Core"></a>   
## <a name="core-runtime-changes"></a>Изменения в среде выполнения ядра  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Сериализация <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>|Объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, сериализованный в .NET Framework 4.5 с помощью <xref:System.Runtime.Serialization.NetDataContractSerializer>, не может быть десериализован в .NET Framework 4.5.1 и 4.5.2 только из-за внутренних изменений в типе.<br /><br /> Это изменение *не* применяется в следующих сценариях.<br /><br /> Объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602> сериализован в .NET Framework 4.5 и десериализован в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. <xref:System.Runtime.Serialization.NetDataContractSerializer> в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] может десериализовать этот объект.<br /><br /> Объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602> сериализован в более поздней версии .NET Framework и десериализован в .NET Framework 4.5. <xref:System.Runtime.Serialization.NetDataContractSerializer> в .NET Framework 4.5 может десериализовать этот объект.<br /><br /> Сериализация и десериализация объекта <xref:System.Collections.Concurrent.ConcurrentDictionary%602> между версиями .NET Framework выше .NET Framework 4.5. Это изменение применимо к объектам, сериализованным *только* с помощью .NET Framework 4.5.|Если необходимо выполнить сериализацию объекта <xref:System.Collections.Concurrent.ConcurrentDictionary%602> в .NET Framework 4.5 и десериализацию в более поздней версии .NET Framework, возможны два обходных пути.<br /><br /> Использование альтернативного сериализатора, например <xref:System.Runtime.Serialization.DataContractSerializer> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.<br /><br /> Обновление до версии [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], поддерживающей десериализацию объекта <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, сериализованного в .NET Framework 4.5.|Дополнительный номер|  
|Класс <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>|<xref:System.Diagnostics.Tracing.EventListener> усекает строки с внедренными символами NULL. Символы NULL не поддерживаются классом <xref:System.Diagnostics.Tracing.EventSource>.|Это изменение влияет только на приложения, использующие <xref:System.Diagnostics.Tracing.EventListener> для чтения данных <xref:System.Diagnostics.Tracing.EventSource> в процессе и символы NULL в качестве разделителей.|Пограничный случай|  
|Класс <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>|В среде выполнения теперь реализуется контракт, задающий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource> и определяющий метод событий ETW, должен вызвать метод <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.|Если <xref:System.Diagnostics.Tracing.EventListener> считывает данные <xref:System.Diagnostics.Tracing.EventSource> в процессе для источника события, нарушающего контракт, то вызывается исключение <xref:System.IndexOutOfRangeException>.<br /><br /> См. раздел [Устранение рисков: вызовы метода EventSource.WriteEvent](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)|Дополнительный номер|  
|Десериализация объектов между доменами приложений|В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.|Эта проблема возникает в очень специфичных условиях. Дополнительные сведения и информацию об устранении рисков см. в разделе [Устранение рисков: десериализация объектов между доменами приложений](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|Пограничный случай|  
|Метод <xref:System.IO.Stream.Dispose%2A?displayProperty=fullName>|В приложениях [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] адаптеры потоков [!INCLUDE[wrt](../../../includes/wrt-md.md)] больше не вызывают метод <xref:System.IO.Stream.FlushAsync%2A> из метода <xref:System.IO.Stream.Dispose%2A>.|Это изменение должно быть прозрачным. Разработчики могут восстановить прежнее поведение, написав следующий код.<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|Прозрачный|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Изменения среды выполнения Windows Communication Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Параметр конфигурации [minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx)|Параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF. Он предназначен для предотвращения возникновения исключений <xref:System.OutOfMemoryException>. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] этот параметр не оказывает никакого влияния. В [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] параметр используется.|Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации. Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.<br /><br /> См. раздел [Устранение рисков: параметр конфигурации minFreeMemoryPercentageToActiveService](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md).|Дополнительный номер|  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [Совместимость приложений в 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Совместимость приложений в 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
