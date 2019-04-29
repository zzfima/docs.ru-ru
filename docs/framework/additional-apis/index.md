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
ms.openlocfilehash: a48a145cd337a18c4ce63b281e1c82032d0532e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675368"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="6d2b7-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="6d2b7-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="6d2b7-103">.NET Framework постоянно развивается.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="6d2b7-104">Для улучшения кросс платформенной разработки и добавления новых функциональных возможностей раньше, новых функций представлены в виде внештатных выпусков (OOB).</span><span class="sxs-lookup"><span data-stu-id="6d2b7-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="6d2b7-105">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="6d2b7-106">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="6d2b7-107">Например <xref:System.Text.CodePagesEncodingProvider> класс делает кодировок кодовых страниц доступными для приложений универсальной платформы Windows, разработанных с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="6d2b7-108">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="6d2b7-109">Встроенные проекты</span><span class="sxs-lookup"><span data-stu-id="6d2b7-109">OOB projects</span></span>
  
| <span data-ttu-id="6d2b7-110">Проект</span><span class="sxs-lookup"><span data-stu-id="6d2b7-110">Project</span></span> | <span data-ttu-id="6d2b7-111">Описание</span><span class="sxs-lookup"><span data-stu-id="6d2b7-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="6d2b7-112">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="6d2b7-113">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="6d2b7-114">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="6d2b7-115">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="6d2b7-116">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="6d2b7-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="6d2b7-117">Проект</span><span class="sxs-lookup"><span data-stu-id="6d2b7-117">Project</span></span> | <span data-ttu-id="6d2b7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6d2b7-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="6d2b7-119">Расширяет <xref:System.Text.EncodingProvider> класса, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальной платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="6d2b7-120">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="6d2b7-120">Private APIs</span></span>  

<span data-ttu-id="6d2b7-121">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="6d2b7-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="6d2b7-122">Имя API</span><span class="sxs-lookup"><span data-stu-id="6d2b7-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="6d2b7-123">Класс System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="6d2b7-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="6d2b7-124">System.Net.Connection.m\_WriteList поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="6d2b7-125">Класс System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="6d2b7-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="6d2b7-126">System.Net.ConnectionGroup.m\_ConnectionList поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="6d2b7-127">Класс System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="6d2b7-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="6d2b7-128">System.Net.CoreResponseData.m\_ResponseHeaders поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="6d2b7-129">System.Net.CoreResponseData.m\_поле StatusCode</span><span class="sxs-lookup"><span data-stu-id="6d2b7-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="6d2b7-130">System.Net.HttpWebRequest. \_AutoRedirects поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="6d2b7-131">System.Net.HttpWebRequest.\_CoreResponse Field</span><span class="sxs-lookup"><span data-stu-id="6d2b7-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="6d2b7-132">System.Net.HttpWebRequest.\_HttpResponse Field</span><span class="sxs-lookup"><span data-stu-id="6d2b7-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="6d2b7-133">System.Net.ServicePoint.m\_ConnectionGroupList поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="6d2b7-134">System.Net.ServicePointManager.s\_ServicePointTable поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="6d2b7-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes поля</span><span class="sxs-lookup"><span data-stu-id="6d2b7-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="6d2b7-136">Класс System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="6d2b7-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="6d2b7-137">Класс System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="6d2b7-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="6d2b7-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6d2b7-138">See also</span></span>

- [<span data-ttu-id="6d2b7-139">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="6d2b7-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
