---
title: "Изменения среды выполнения в .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "совместимость приложений"
  - "изменения среды выполнения"
  - ".NET Framework 4.5.1"
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Изменения среды выполнения в .NET Framework 4.5.1
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, разработанные для [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] или версии 4.5, но выполняющиеся в версии 4.51. Они включают изменения в следующих областях.  
  
-   [Core](#Core)  
  
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
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> сериализации</TKey, TValue>|Объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602> объект сериализуется в .NET Framework 4.5 с <xref:System.Runtime.Serialization.NetDataContractSerializer> только из-за внутренних изменений в типе не может быть десериализован в .NET Framework 4.5.1 и 4.5.2.\</TKey, TValue><br /><br /> Это изменение *не* применяются в следующих случаях:<br /><br /> Объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602> объекта для сериализации в .NET Framework 4.5 и десериализации в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</TKey, TValue> <xref:System.Runtime.Serialization.NetDataContractSerializer> в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] может десериализовать объект.<br /><br /> Объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602> объекта сериализуются в более поздней версии платформы .NET Framework и десериализуются в .NET Framework 4.5.\</TKey, TValue> <xref:System.Runtime.Serialization.NetDataContractSerializer> в .NET Framework 4.5 является возможность десериализации объекта.<br /><br /> Между версии сериализация и десериализация <xref:System.Collections.Concurrent.ConcurrentDictionary%602> объекта между любой версии платформы .NET Framework после .NET Framework 4.5.</TKey, TValue> Это изменение относится к объектам, сериализуются в .NET Framework 4.5 *только*.|Два способа решения доступны, если это необходимо для сериализации <xref:System.Collections.Concurrent.ConcurrentDictionary%602> объекта .NET Framework 4.5 и его десериализации в более поздней версии платформы .NET Framework:\</TKey, TValue><br /><br /> Использовать альтернативный сериализатор, такие как <xref:System.Runtime.Serialization.DataContractSerializer> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.<br /><br /> Обновление до [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], который поддерживает десериализацию <xref:System.Collections.Concurrent.ConcurrentDictionary%602> объект сериализуется с помощью .NET Framework 4.5.\</TKey, TValue>|Дополнительный номер|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> класса|<xref:System.Diagnostics.Tracing.EventListener> усекает строки с внедренными значениями NULL. Символы NULL не поддерживаются <xref:System.Diagnostics.Tracing.EventSource> класса.|Изменение влияет только на приложения, использующие <xref:System.Diagnostics.Tracing.EventListener> для чтения <xref:System.Diagnostics.Tracing.EventSource> данные в процессе и использовать символы null в качестве разделителей.|Пограничный случай|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> класса|Среда выполнения теперь реализуется контракт, задающий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource> , определяющий ETW метод событий необходимо вызвать базовый класс <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> метод с Идентификатором события следуют те же аргументы, которые был передан метод событий ETW.|<xref:System.IndexOutOfRangeException> исключение, если <xref:System.Diagnostics.Tracing.EventListener> считывает <xref:System.Diagnostics.Tracing.EventSource> данных в процессе для источника события, нарушающего контракт.<br /><br /> В разделе [Устранение: вызовы метода EventSource.WriteEvent](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)|Дополнительный номер|  
|Десериализация объектов между доменами приложений|В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.|Эта проблема возникает в очень специфичных условиях. Дополнительные сведения и устранение см. в разделе [Устранение: десериализации из объектов между доменами приложений](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|Пограничный случай|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName> метод|В [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] приложений, [!INCLUDE[wrt](../../../includes/wrt-md.md)] адаптеров поток больше не вызывают <xref:System.IO.Stream.FlushAsync%2A> метод <xref:System.IO.Stream.Dispose%2A> метод.|Это изменение должно быть прозрачным. Разработчики могут восстановить прежнее поведение, написав следующий код.<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|Прозрачный|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Изменения среды выполнения Windows Communication Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|[minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx) параметр конфигурации|Параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF. Он предназначен для предотвращения <xref:System.OutOfMemoryException> исключения. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] этот параметр не оказывает никакого влияния. В [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] параметр используется.|Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации. Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.<br /><br /> В разделе [Устранение: параметр конфигурации minFreeMemoryPercentageToActiveService](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md).|Дополнительный номер|  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [Совместимость приложений в версии 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Совместимость приложений в 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)