---
title: Дополнительные библиотеки классов и интерфейсы API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155912"
---
# <a name="additional-class-libraries-and-apis"></a>Дополнительные библиотеки классов и интерфейсы API

Рамочная программа .NET постоянно развивается. Для улучшения кросс-платформенной разработки и раннего внедрения новых функциональных возможностей новые функции выходят из группы (OOB). В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.  
  
Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework. Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодовые коды кодовыми кодами доступными для приложений UWP, разработанных с помощью рамочной программы .NET. В этой статье эти библиотеки перечислены тоже.  
  
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
| <xref:System.Text.CodePagesEncodingProvider> | Расширяет <xref:System.Text.EncodingProvider> класс, чтобы сделать кодкодирование страницкода доступным для приложений, ориентированных на платформу Universal Windows. |  
  
## <a name="private-apis"></a>Частные интерфейсы API  

Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.  
  
* [Microsoft.SqlServer.Server.SmiOrderProperty.Item собственности](microsoft.sqlserver.server.smiorderproperty.item.md)
* [Метод System.Exception.PrepForRemoting](system.exception.prepforremoting.md)
* [Недвижимость System.Data.SqlTypes.SqlChars.Stream](system.data.sqltypes.sqlchars.stream.md)
* [Строитель System.Data.SqlTypes.SqlStreamChars](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [System.Data.SqlTypes.SqlStreamChars.CanSeek Property](system.data.sqltypes.sqlstreamchars.canseek.md)
* [System.Data.SqlTypes.SqlStreamChars.IsNull Property](system.data.sqltypes.sqlstreamchars.isnull.md)
* [System.Data.SqlTypes.SqlStreamChars.Length Property](system.data.sqltypes.sqlstreamchars.length.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.Close](system.data.sqltypes.sqlstreamchars.close.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.Dispose](system.data.sqltypes.sqlstreamchars.dispose.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.Flush](system.data.sqltypes.sqlstreamchars.flush.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.Read](system.data.sqltypes.sqlstreamchars.read.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.Seek](system.data.sqltypes.sqlstreamchars.seek.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.SetМетод](system.data.sqltypes.sqlstreamchars.setlength.md)
* [Метод System.Data.SqlTypes.SqlStreamChars.Write](system.data.sqltypes.sqlstreamchars.write.md)
* [Метод System.IO.Memorystream.InternalgetOriginandAndLength Метод](system.io.memorystream.internalgetoriginandlength.md)
* [Класс Подключения System.Net.](connection.md)
* [System.Net.Connection.m\_WriteList Поле](m_writelist.md)
* [Класс System.Net.ConnectionGroup](connectiongroup.md)
* [System.Net.ConnectionGroup.m\_ConnectionList Field](m_connectionlist.md)
* [Недвижимость System.Net.ConnectStream.Connection](system.net.connectstream.connection.md)
* [Класс System.Net.CoreResponseData](coreresponsedata.md)
* [System.Net.CoreResponseData.m\_ResponseHeaders Field](coreresponsedata_m_responseheaders.md)
* [System.Net.CoreResponseData.m\_StatusCode Field](coreresponsedata_m_statuscode.md)
* [System.net.httpwebRequest. \_АвтоРенаправляет поле](_autoredirects.md)
* [System.net.httpwebRequest. \_Поле CoreResponse](httpwebrequest__coreresponse.md)
* [System.net.httpwebRequest. \_Поле httpResponse](_httpresponse.md)
* [Недвижимость System.Net.PooledStream.NetworkStream](system.net.pooledstream.networkstream.md)
* [Класс System.Net.RtcState](system.net.rtcstate.md)
* [System.Net.ServicePoint.m\_ConnectionGroupList Поле](m_connectiongrouplist.md)
* [System.Net.ServicePointManager.s\_ServicePointTable Поле](s_servicepointtable.md)
* [System.Net.TlsStream.m_Worker Поле](system.net.tlsstream.m_worker.md)
* [Недвижимость System.Net.Security.Sslstate.SslProtocol](system.net.security.sslstate.sslprotocol.md)
* [Метод System.ServiceModel.channels.message.BodyTostring](system.servicemodel.channels.message.bodytostring.md)
* [Метод System.ServiceModel.Channels.Message.WriteStartHeaders](system.servicemodel.channels.message.writestartheaders.md)
* [System.Windows.Diagnostics.VisualDiagnostics.s\_является DebuggerCheckDisabledForTestPurposes Поле](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Класс System.Windows.Forms.Design.DataMemberFieldEditor Класс](datamemberfieldeditor-class.md)
* [System.Windows.Forms.Design.DataMemberListEditor Класс](datamemberlisteditor-class.md)
* [Метод System.Xml.XmlReader.CreateSqlReader](system.xml.xmlreader.createsqlreader.md)
* [Adodb. Интерфейс подключения](adodb.connection.md)
* [Adodb. EventReason Enum](adodb.eventreasonenum.md)
* [Adodb. EventStatus Enum](adodb.eventstatusenum.md)
* [stdole. Структура DISPPARAMS](stdole.dispparams.md)
* [stdole. Структура EXCEPINFO](stdole.excepinfo.md)
* [stdole. IFont.Name недвижимость](stdole.ifont.name.md)
* [stdole. Интерфейс IFontDisp](stdole.ifontdisp.md)
* [stdole. Недвижимость IPicture.Handle](stdole.ipicture.handle.md)
* [stdole. Недвижимость IPictureDisp.Handle](stdole.ipicturedisp.handle.md)
* [stdole. Интерфейс StdFont](stdole.stdfont.md)
* [stdole. Интерфейс StdPicture](stdole.stdpicture.md)
  
## <a name="see-also"></a>См. также раздел

* [.NET Framework и отдельные выпуски](../get-started/the-net-framework-and-out-of-band-releases.md)
