---
title: Дополнительные библиотеки классов и интерфейсы API
ms.date: 10/09/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: b869ca2f5e17db9a204a8b757b5e24ebb209d7c5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395664"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="50701-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="50701-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="50701-103">.NET Framework постоянно развивается.</span><span class="sxs-lookup"><span data-stu-id="50701-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="50701-104">Для улучшения разработки кросс-платформенного процесса и появления новых функций на ранних этапах новые функции выпускаются с использованием аппаратного контроллера управления (OOB).</span><span class="sxs-lookup"><span data-stu-id="50701-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="50701-105">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="50701-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="50701-106">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50701-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="50701-107">Например, класс <xref:System.Text.CodePagesEncodingProvider> делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50701-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="50701-108">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="50701-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="50701-109">Внештатные проекты</span><span class="sxs-lookup"><span data-stu-id="50701-109">OOB projects</span></span>
  
| <span data-ttu-id="50701-110">Проект</span><span class="sxs-lookup"><span data-stu-id="50701-110">Project</span></span> | <span data-ttu-id="50701-111">Описание</span><span class="sxs-lookup"><span data-stu-id="50701-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="50701-112">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="50701-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="50701-113">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="50701-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="50701-114">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="50701-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="50701-115">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="50701-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="50701-116">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="50701-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="50701-117">Проект</span><span class="sxs-lookup"><span data-stu-id="50701-117">Project</span></span> | <span data-ttu-id="50701-118">Описание</span><span class="sxs-lookup"><span data-stu-id="50701-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="50701-119">Расширяет класс <xref:System.Text.EncodingProvider>, чтобы кодировки кодовых страниц были доступны для приложений, предназначенных для универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="50701-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="50701-120">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="50701-120">Private APIs</span></span>  

<span data-ttu-id="50701-121">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="50701-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="50701-122">Свойство Microsoft. SqlServer. Server. Смиордерпроперти. Item</span><span class="sxs-lookup"><span data-stu-id="50701-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="50701-123">Метод System. Exception. Препфорремотинг</span><span class="sxs-lookup"><span data-stu-id="50701-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="50701-124">Свойство System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="50701-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="50701-125">Конструктор System. Data. SqlTypes. Склстреамчарс</span><span class="sxs-lookup"><span data-stu-id="50701-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="50701-126">Свойство System. Data. SqlTypes. Склстреамчарс. CanSeek</span><span class="sxs-lookup"><span data-stu-id="50701-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="50701-127">Свойство System. Data. SqlTypes. Склстреамчарс. IsNull</span><span class="sxs-lookup"><span data-stu-id="50701-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="50701-128">Свойство System. Data. SqlTypes. Склстреамчарс. length</span><span class="sxs-lookup"><span data-stu-id="50701-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="50701-129">Метод System. Data. SqlTypes. Склстреамчарс. Close</span><span class="sxs-lookup"><span data-stu-id="50701-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="50701-130">Метод System. Data. SqlTypes. Склстреамчарс. Dispose</span><span class="sxs-lookup"><span data-stu-id="50701-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="50701-131">Метод System. Data. SqlTypes. Склстреамчарс. Flush</span><span class="sxs-lookup"><span data-stu-id="50701-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="50701-132">Метод System. Data. SqlTypes. Склстреамчарс. Read</span><span class="sxs-lookup"><span data-stu-id="50701-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="50701-133">Метод System. Data. SqlTypes. Склстреамчарс. Seek</span><span class="sxs-lookup"><span data-stu-id="50701-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="50701-134">Метод System. Data. SqlTypes. Склстреамчарс. SetLength</span><span class="sxs-lookup"><span data-stu-id="50701-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="50701-135">Метод System. Data. SqlTypes. Склстреамчарс. Write</span><span class="sxs-lookup"><span data-stu-id="50701-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="50701-136">Класс System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="50701-136">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="50701-137">System .NET. Connection. m @ no__t-1WriteList поле</span><span class="sxs-lookup"><span data-stu-id="50701-137">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="50701-138">Класс System .NET. Коннектионграуп</span><span class="sxs-lookup"><span data-stu-id="50701-138">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="50701-139">System .NET. Коннектионграуп. m @ no__t-1ConnectionList поле</span><span class="sxs-lookup"><span data-stu-id="50701-139">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="50701-140">Класс System .NET. Коререспонседата</span><span class="sxs-lookup"><span data-stu-id="50701-140">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="50701-141">System .NET. Коререспонседата. m @ no__t-1ResponseHeaders поле</span><span class="sxs-lookup"><span data-stu-id="50701-141">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="50701-142">System .NET. Коререспонседата. m @ no__t-1StatusCode поле</span><span class="sxs-lookup"><span data-stu-id="50701-142">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="50701-143">Поле System .NET. HttpWebRequest. \_AutoRedirects</span><span class="sxs-lookup"><span data-stu-id="50701-143">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="50701-144">Поле System .NET. HttpWebRequest. \_CoreResponse</span><span class="sxs-lookup"><span data-stu-id="50701-144">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="50701-145">Поле System .NET. HttpWebRequest. \_HttpResponse</span><span class="sxs-lookup"><span data-stu-id="50701-145">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="50701-146">System .NET. ServicePoint. m @ no__t-1ConnectionGroupList поле</span><span class="sxs-lookup"><span data-stu-id="50701-146">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="50701-147">System .NET. ServicePointManager. s @ no__t-1ServicePointTable поле</span><span class="sxs-lookup"><span data-stu-id="50701-147">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="50701-148">System. Windows. Diagnostics. Висуалдиагностикс. s @ no__t-1isDebuggerCheckDisabledForTestPurposes поле</span><span class="sxs-lookup"><span data-stu-id="50701-148">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="50701-149">Класс System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="50701-149">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="50701-150">Класс System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="50701-150">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="50701-151">ADODB. Интерфейс подключения</span><span class="sxs-lookup"><span data-stu-id="50701-151">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="50701-152">ADODB. Перечисление Евентреасон</span><span class="sxs-lookup"><span data-stu-id="50701-152">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="50701-153">ADODB. Перечисление Евентстатус</span><span class="sxs-lookup"><span data-stu-id="50701-153">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="50701-154">стдоле. Структура DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="50701-154">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="50701-155">стдоле. Структура ЕКСЦЕПИНФО</span><span class="sxs-lookup"><span data-stu-id="50701-155">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="50701-156">стдоле. IFont.Name, свойство</span><span class="sxs-lookup"><span data-stu-id="50701-156">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="50701-157">стдоле. Интерфейс IFontDisp</span><span class="sxs-lookup"><span data-stu-id="50701-157">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="50701-158">стдоле. Ипиктуре. Handle, свойство</span><span class="sxs-lookup"><span data-stu-id="50701-158">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="50701-159">стдоле. Ипиктуредисп. Handle, свойство</span><span class="sxs-lookup"><span data-stu-id="50701-159">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="50701-160">стдоле. Интерфейс Стдфонт</span><span class="sxs-lookup"><span data-stu-id="50701-160">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="50701-161">стдоле. Интерфейс Стдпиктуре</span><span class="sxs-lookup"><span data-stu-id="50701-161">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="50701-162">См. также</span><span class="sxs-lookup"><span data-stu-id="50701-162">See also</span></span>

* [<span data-ttu-id="50701-163">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="50701-163">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
