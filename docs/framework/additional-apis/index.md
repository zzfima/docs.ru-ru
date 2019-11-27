---
title: Дополнительные библиотеки классов и интерфейсы API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: e1e2af584c73b1c0b2548cdd3fcbd8517dfa330d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429340"
---
# <a name="additional-class-libraries-and-apis"></a>Дополнительные библиотеки классов и интерфейсы API

.NET Framework постоянно развивается. Для улучшения разработки кросс-платформенного процесса и появления новых функций на ранних этапах новые функции выпускаются с использованием аппаратного контроллера управления (OOB). В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.  
  
Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework. Например, класс <xref:System.Text.CodePagesEncodingProvider> делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework. В этой статье эти библиотеки перечислены тоже.  
  
## <a name="oob-projects"></a>Внештатные проекты
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется. |
| <xref:System.Net.Http.WinHttpHandler> | Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows. |
| <xref:System.Numerics> | Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма. |  

## <a name="platform-specific-libraries"></a>Библиотеки для конкретных платформ
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Расширяет класс <xref:System.Text.EncodingProvider>, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальная платформа Windows. |  
  
## <a name="private-apis"></a>Частные интерфейсы API  

Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.  
  
* [Свойство Microsoft. SqlServer. Server. Смиордерпроперти. Item](microsoft.sqlserver.server.smiorderproperty.item.md)
* [Метод System. Exception. Препфорремотинг](system.exception.prepforremoting.md)
* [Свойство System. Data. SqlTypes. SqlChars. Stream](system.data.sqltypes.sqlchars.stream.md)
* [Конструктор System. Data. SqlTypes. Склстреамчарс](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [Свойство System. Data. SqlTypes. Склстреамчарс. CanSeek](system.data.sqltypes.sqlstreamchars.canseek.md)
* [Свойство System. Data. SqlTypes. Склстреамчарс. IsNull](system.data.sqltypes.sqlstreamchars.isnull.md)
* [Свойство System. Data. SqlTypes. Склстреамчарс. length](system.data.sqltypes.sqlstreamchars.length.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Close](system.data.sqltypes.sqlstreamchars.close.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Dispose](system.data.sqltypes.sqlstreamchars.dispose.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Flush](system.data.sqltypes.sqlstreamchars.flush.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Read](system.data.sqltypes.sqlstreamchars.read.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Seek](system.data.sqltypes.sqlstreamchars.seek.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. SetLength](system.data.sqltypes.sqlstreamchars.setlength.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Write](system.data.sqltypes.sqlstreamchars.write.md)
* [Метод System. IO. MemoryStream. Интерналжеторигинандленгс](system.io.memorystream.internalgetoriginandlength.md)
* [Класс System .NET. Connection](connection.md)
* [Система .NET. Connection. m\_поле Врителист](m_writelist.md)
* [Класс System .NET. Коннектионграуп](connectiongroup.md)
* [System .NET. Коннектионграуп. m\_поле Коннектионлист](m_connectionlist.md)
* [Свойство System .NET. Коннектстреам. Connection](system.net.connectstream.connection.md)
* [Класс System .NET. Коререспонседата](coreresponsedata.md)
* [System .NET. Коререспонседата. m\_поле ResponseHeaders](coreresponsedata_m_responseheaders.md)
* [System .NET. Коререспонседата. m\_поле StatusCode](coreresponsedata_m_statuscode.md)
* [System .NET. HttpWebRequest.\_поле перенаправления](_autoredirects.md)
* [System .NET. HttpWebRequest.\_Коререспонсе поле](httpwebrequest__coreresponse.md)
* [System .NET. HttpWebRequest.\_HttpResponse поле](_httpresponse.md)
* [Свойство System .NET. Пуледстреам. NetworkStream](system.net.pooledstream.networkstream.md)
* [Класс System .NET. Рткстате](system.net.rtcstate.md)
* [System .NET. ServicePoint. m\_поле Коннектионграуплист](m_connectiongrouplist.md)
* [System .NET. ServicePointManager. s\_поле Сервицепоинттабле](s_servicepointtable.md)
* [Поле System .NET. Тлсстреам. m_Worker](system.net.tlsstream.m_worker.md)
* [Свойство System .NET. Security. Сслстате. Сслпротокол](system.net.security.sslstate.sslprotocol.md)
* [Метод System. ServiceModel. Channels. Message. Бодитостринг](system.servicemodel.channels.message.bodytostring.md)
* [Метод System. ServiceModel. Channels. Message. Вритестарсеадерс](system.servicemodel.channels.message.writestartheaders.md)
* [System. Windows. Diagnostics. Висуалдиагностикс. s\_поле Исдебугжерчеккдисабледфортестпурпосес](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Класс System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Класс System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md)
* [Метод System. XML. XmlReader. Креатесклреадер](system.xml.xmlreader.createsqlreader.md)
* [ADODB. Интерфейс подключения](adodb.connection.md)
* [ADODB. Перечисление Евентреасон](adodb.eventreasonenum.md)
* [ADODB. Перечисление Евентстатус](adodb.eventstatusenum.md)
* [стдоле. Структура DISPPARAMS](stdole.dispparams.md)
* [стдоле. Структура ЕКСЦЕПИНФО](stdole.excepinfo.md)
* [стдоле. IFont.Name, свойство](stdole.ifont.name.md)
* [стдоле. Интерфейс IFontDisp](stdole.ifontdisp.md)
* [стдоле. Ипиктуре. Handle, свойство](stdole.ipicture.handle.md)
* [стдоле. Ипиктуредисп. Handle, свойство](stdole.ipicturedisp.handle.md)
* [стдоле. Интерфейс Стдфонт](stdole.stdfont.md)
* [стдоле. Интерфейс Стдпиктуре](stdole.stdpicture.md)
  
## <a name="see-also"></a>См. также:

* [.NET Framework и отдельные выпуски](../get-started/the-net-framework-and-out-of-band-releases.md)
