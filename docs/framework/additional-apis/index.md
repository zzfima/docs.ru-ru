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
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="aa323-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="aa323-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="aa323-103">Рамочная программа .NET постоянно развивается.</span><span class="sxs-lookup"><span data-stu-id="aa323-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="aa323-104">Для улучшения кросс-платформенной разработки и раннего внедрения новых функциональных возможностей новые функции выходят из группы (OOB).</span><span class="sxs-lookup"><span data-stu-id="aa323-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="aa323-105">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="aa323-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="aa323-106">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa323-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="aa323-107">Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодовые коды кодовыми кодами доступными для приложений UWP, разработанных с помощью рамочной программы .NET.</span><span class="sxs-lookup"><span data-stu-id="aa323-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="aa323-108">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="aa323-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="aa323-109">Внештатные проекты</span><span class="sxs-lookup"><span data-stu-id="aa323-109">OOB projects</span></span>
  
| <span data-ttu-id="aa323-110">Проект</span><span class="sxs-lookup"><span data-stu-id="aa323-110">Project</span></span> | <span data-ttu-id="aa323-111">Описание</span><span class="sxs-lookup"><span data-stu-id="aa323-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="aa323-112">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="aa323-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="aa323-113">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="aa323-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="aa323-114">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="aa323-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="aa323-115">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="aa323-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="aa323-116">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="aa323-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="aa323-117">Проект</span><span class="sxs-lookup"><span data-stu-id="aa323-117">Project</span></span> | <span data-ttu-id="aa323-118">Описание</span><span class="sxs-lookup"><span data-stu-id="aa323-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="aa323-119">Расширяет <xref:System.Text.EncodingProvider> класс, чтобы сделать кодкодирование страницкода доступным для приложений, ориентированных на платформу Universal Windows.</span><span class="sxs-lookup"><span data-stu-id="aa323-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="aa323-120">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="aa323-120">Private APIs</span></span>  

<span data-ttu-id="aa323-121">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="aa323-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="aa323-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item собственности</span><span class="sxs-lookup"><span data-stu-id="aa323-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="aa323-123">Метод System.Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="aa323-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="aa323-124">Недвижимость System.Data.SqlTypes.SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="aa323-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="aa323-125">Строитель System.Data.SqlTypes.SqlStreamChars</span><span class="sxs-lookup"><span data-stu-id="aa323-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="aa323-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span><span class="sxs-lookup"><span data-stu-id="aa323-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="aa323-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span><span class="sxs-lookup"><span data-stu-id="aa323-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="aa323-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span><span class="sxs-lookup"><span data-stu-id="aa323-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="aa323-129">Метод System.Data.SqlTypes.SqlStreamChars.Close</span><span class="sxs-lookup"><span data-stu-id="aa323-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="aa323-130">Метод System.Data.SqlTypes.SqlStreamChars.Dispose</span><span class="sxs-lookup"><span data-stu-id="aa323-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="aa323-131">Метод System.Data.SqlTypes.SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="aa323-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="aa323-132">Метод System.Data.SqlTypes.SqlStreamChars.Read</span><span class="sxs-lookup"><span data-stu-id="aa323-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="aa323-133">Метод System.Data.SqlTypes.SqlStreamChars.Seek</span><span class="sxs-lookup"><span data-stu-id="aa323-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="aa323-134">Метод System.Data.SqlTypes.SqlStreamChars.SetМетод</span><span class="sxs-lookup"><span data-stu-id="aa323-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="aa323-135">Метод System.Data.SqlTypes.SqlStreamChars.Write</span><span class="sxs-lookup"><span data-stu-id="aa323-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="aa323-136">Метод System.IO.Memorystream.InternalgetOriginandAndLength Метод</span><span class="sxs-lookup"><span data-stu-id="aa323-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="aa323-137">Класс Подключения System.Net.</span><span class="sxs-lookup"><span data-stu-id="aa323-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="aa323-138">System.Net.Connection.m\_WriteList Поле</span><span class="sxs-lookup"><span data-stu-id="aa323-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="aa323-139">Класс System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="aa323-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="aa323-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="aa323-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="aa323-141">Недвижимость System.Net.ConnectStream.Connection</span><span class="sxs-lookup"><span data-stu-id="aa323-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="aa323-142">Класс System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="aa323-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="aa323-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="aa323-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="aa323-144">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="aa323-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="aa323-145">System.net.httpwebRequest. \_АвтоРенаправляет поле</span><span class="sxs-lookup"><span data-stu-id="aa323-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="aa323-146">System.net.httpwebRequest. \_Поле CoreResponse</span><span class="sxs-lookup"><span data-stu-id="aa323-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="aa323-147">System.net.httpwebRequest. \_Поле httpResponse</span><span class="sxs-lookup"><span data-stu-id="aa323-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="aa323-148">Недвижимость System.Net.PooledStream.NetworkStream</span><span class="sxs-lookup"><span data-stu-id="aa323-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="aa323-149">Класс System.Net.RtcState</span><span class="sxs-lookup"><span data-stu-id="aa323-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="aa323-150">System.Net.ServicePoint.m\_ConnectionGroupList Поле</span><span class="sxs-lookup"><span data-stu-id="aa323-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="aa323-151">System.Net.ServicePointManager.s\_ServicePointTable Поле</span><span class="sxs-lookup"><span data-stu-id="aa323-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="aa323-152">System.Net.TlsStream.m_Worker Поле</span><span class="sxs-lookup"><span data-stu-id="aa323-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="aa323-153">Недвижимость System.Net.Security.Sslstate.SslProtocol</span><span class="sxs-lookup"><span data-stu-id="aa323-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="aa323-154">Метод System.ServiceModel.channels.message.BodyTostring</span><span class="sxs-lookup"><span data-stu-id="aa323-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="aa323-155">Метод System.ServiceModel.Channels.Message.WriteStartHeaders</span><span class="sxs-lookup"><span data-stu-id="aa323-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="aa323-156">System.Windows.Diagnostics.VisualDiagnostics.s\_является DebuggerCheckDisabledForTestPurposes Поле</span><span class="sxs-lookup"><span data-stu-id="aa323-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="aa323-157">Класс System.Windows.Forms.Design.DataMemberFieldEditor Класс</span><span class="sxs-lookup"><span data-stu-id="aa323-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="aa323-158">System.Windows.Forms.Design.DataMemberListEditor Класс</span><span class="sxs-lookup"><span data-stu-id="aa323-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="aa323-159">Метод System.Xml.XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="aa323-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="aa323-160">Adodb. Интерфейс подключения</span><span class="sxs-lookup"><span data-stu-id="aa323-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="aa323-161">Adodb. EventReason Enum</span><span class="sxs-lookup"><span data-stu-id="aa323-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="aa323-162">Adodb. EventStatus Enum</span><span class="sxs-lookup"><span data-stu-id="aa323-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="aa323-163">stdole. Структура DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="aa323-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="aa323-164">stdole. Структура EXCEPINFO</span><span class="sxs-lookup"><span data-stu-id="aa323-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="aa323-165">stdole. IFont.Name недвижимость</span><span class="sxs-lookup"><span data-stu-id="aa323-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="aa323-166">stdole. Интерфейс IFontDisp</span><span class="sxs-lookup"><span data-stu-id="aa323-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="aa323-167">stdole. Недвижимость IPicture.Handle</span><span class="sxs-lookup"><span data-stu-id="aa323-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="aa323-168">stdole. Недвижимость IPictureDisp.Handle</span><span class="sxs-lookup"><span data-stu-id="aa323-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="aa323-169">stdole. Интерфейс StdFont</span><span class="sxs-lookup"><span data-stu-id="aa323-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="aa323-170">stdole. Интерфейс StdPicture</span><span class="sxs-lookup"><span data-stu-id="aa323-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="aa323-171">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa323-171">See also</span></span>

* [<span data-ttu-id="aa323-172">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="aa323-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
