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
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="4821a-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="4821a-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="4821a-103">.NET Framework постоянно развивается.</span><span class="sxs-lookup"><span data-stu-id="4821a-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="4821a-104">Для улучшения разработки кросс-платформенного процесса и появления новых функций на ранних этапах новые функции выпускаются с использованием аппаратного контроллера управления (OOB).</span><span class="sxs-lookup"><span data-stu-id="4821a-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="4821a-105">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="4821a-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="4821a-106">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4821a-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="4821a-107">Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4821a-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="4821a-108">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="4821a-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="4821a-109">Встроенные проекты</span><span class="sxs-lookup"><span data-stu-id="4821a-109">OOB projects</span></span>
  
| <span data-ttu-id="4821a-110">Проект</span><span class="sxs-lookup"><span data-stu-id="4821a-110">Project</span></span> | <span data-ttu-id="4821a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4821a-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="4821a-112">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="4821a-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="4821a-113">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="4821a-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="4821a-114">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="4821a-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="4821a-115">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="4821a-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="4821a-116">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="4821a-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="4821a-117">Проект</span><span class="sxs-lookup"><span data-stu-id="4821a-117">Project</span></span> | <span data-ttu-id="4821a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4821a-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="4821a-119"><xref:System.Text.EncodingProvider> Расширяет класс, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="4821a-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="4821a-120">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="4821a-120">Private APIs</span></span>  

<span data-ttu-id="4821a-121">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="4821a-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="4821a-122">Имя API</span><span class="sxs-lookup"><span data-stu-id="4821a-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="4821a-123">Класс System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="4821a-123">System.Net.Connection Class</span></span>](connection.md) |
| [<span data-ttu-id="4821a-124">Поле системы .NET. Connection.\_m врителист</span><span class="sxs-lookup"><span data-stu-id="4821a-124">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md) |
| [<span data-ttu-id="4821a-125">Класс System .NET. Коннектионграуп</span><span class="sxs-lookup"><span data-stu-id="4821a-125">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md) |
| [<span data-ttu-id="4821a-126">System .NET. коннектионграуп. m\_коннектионлист, поле</span><span class="sxs-lookup"><span data-stu-id="4821a-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md) |
| [<span data-ttu-id="4821a-127">Класс System .NET. Коререспонседата</span><span class="sxs-lookup"><span data-stu-id="4821a-127">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md) |
| [<span data-ttu-id="4821a-128">System .NET. коререспонседата. m\_ResponseHeaders, поле</span><span class="sxs-lookup"><span data-stu-id="4821a-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="4821a-129">Поле StatusCode System .NET. коререспонседата\_. m</span><span class="sxs-lookup"><span data-stu-id="4821a-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="4821a-130">System .NET. HttpWebRequest. \_Поле перенаправлений</span><span class="sxs-lookup"><span data-stu-id="4821a-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md) |
| [<span data-ttu-id="4821a-131">System .NET. HttpWebRequest. \_Поле коререспонсе</span><span class="sxs-lookup"><span data-stu-id="4821a-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="4821a-132">System .NET. HttpWebRequest. \_Поле HttpResponse</span><span class="sxs-lookup"><span data-stu-id="4821a-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md) |
| [<span data-ttu-id="4821a-133">System .NET. ServicePoint. m\_коннектионграуплист, поле</span><span class="sxs-lookup"><span data-stu-id="4821a-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md) |
| [<span data-ttu-id="4821a-134">Поле System .NET. ServicePointManager.\_s сервицепоинттабле</span><span class="sxs-lookup"><span data-stu-id="4821a-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md) |
| [<span data-ttu-id="4821a-135">System. Windows. Diagnostics. висуалдиагностикс. s\_исдебугжерчеккдисабледфортестпурпосес, поле</span><span class="sxs-lookup"><span data-stu-id="4821a-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="4821a-136">Класс System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="4821a-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md) |
| [<span data-ttu-id="4821a-137">Класс System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="4821a-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="4821a-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4821a-138">See also</span></span>

- [<span data-ttu-id="4821a-139">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="4821a-139">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
