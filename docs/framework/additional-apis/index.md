---
title: Дополнительные библиотеки классов и интерфейсы API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053246"
---
# <a name="additional-class-libraries-and-apis"></a>Дополнительные библиотеки классов и интерфейсы API

.NET Framework постоянно развивается. Для улучшения разработки кросс-платформенного процесса и появления новых функций на ранних этапах новые функции выпускаются с использованием аппаратного контроллера управления (OOB). В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.  
  
Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework. Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework. В этой статье эти библиотеки перечислены тоже.  
  
## <a name="oob-projects"></a>Встроенные проекты
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется. |
| <xref:System.Net.Http.WinHttpHandler> | Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows. |
| <xref:System.Numerics> | Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма. |  

## <a name="platform-specific-libraries"></a>Библиотеки для конкретных платформ
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <xref:System.Text.EncodingProvider> Расширяет класс, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальная платформа Windows. |  
  
## <a name="private-apis"></a>Частные интерфейсы API  

Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.  
  
| Имя API |
| -------- |
| [Класс System .NET. Connection](connection.md) |
| [Поле системы .NET. Connection.\_m врителист](m_writelist.md) |
| [Класс System .NET. Коннектионграуп](connectiongroup.md) |
| [System .NET. коннектионграуп. m\_коннектионлист, поле](m_connectionlist.md) |
| [Класс System .NET. Коререспонседата](coreresponsedata.md) |
| [System .NET. коререспонседата. m\_ResponseHeaders, поле](coreresponsedata_m_responseheaders.md) |
| [Поле StatusCode System .NET. коререспонседата\_. m](coreresponsedata_m_statuscode.md) |
| [System .NET. HttpWebRequest. \_Поле перенаправлений](_autoredirects.md) |
| [System .NET. HttpWebRequest. \_Поле коререспонсе](httpwebrequest__coreresponse.md) |
| [System .NET. HttpWebRequest. \_Поле HttpResponse](_httpresponse.md) |
| [System .NET. ServicePoint. m\_коннектионграуплист, поле](m_connectiongrouplist.md) |
| [Поле System .NET. ServicePointManager.\_s сервицепоинттабле](s_servicepointtable.md) |
| [System. Windows. Diagnostics. висуалдиагностикс. s\_исдебугжерчеккдисабледфортестпурпосес, поле](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [Класс System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md) |
| [Класс System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>См. также

- [.NET Framework и отдельные выпуски](../get-started/the-net-framework-and-out-of-band-releases.md)
