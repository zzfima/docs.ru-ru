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
ms.openlocfilehash: bdba02feb8cacc6ab1886c12f88716184aa2a81a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="7d42c-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="7d42c-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="7d42c-103">Платформа .NET Framework постоянно развивается. С целью совершенствования кроссплатформенной разработки и оперативного предоставления новых функциональных возможностей нашим клиентам мы выпускаем новые возможности в виде внештатных выпусков.</span><span class="sxs-lookup"><span data-stu-id="7d42c-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="7d42c-104">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="7d42c-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="7d42c-105">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d42c-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="7d42c-106">Например <xref:System.Text.CodePagesEncodingProvider> класса делает доступными для приложений UWP, разработанных с помощью .NET Framework кодировок кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="7d42c-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="7d42c-107">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="7d42c-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="7d42c-108">Встроенные проекты</span><span class="sxs-lookup"><span data-stu-id="7d42c-108">OOB projects</span></span>
  
| <span data-ttu-id="7d42c-109">Проект</span><span class="sxs-lookup"><span data-stu-id="7d42c-109">Project</span></span> | <span data-ttu-id="7d42c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7d42c-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="7d42c-111">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="7d42c-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="7d42c-112">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="7d42c-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="7d42c-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="7d42c-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="7d42c-114">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="7d42c-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="7d42c-115">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="7d42c-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="7d42c-116">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="7d42c-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="7d42c-117">Проект</span><span class="sxs-lookup"><span data-stu-id="7d42c-117">Project</span></span> | <span data-ttu-id="7d42c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7d42c-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="7d42c-119">Расширяет <xref:System.Text.EncodingProvider> класса, чтобы сделать доступными для приложений, предназначенных для универсальной платформы Windows кодировок кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="7d42c-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="7d42c-120">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="7d42c-120">Private APIs</span></span>  

<span data-ttu-id="7d42c-121">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="7d42c-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="7d42c-122">Имя API</span><span class="sxs-lookup"><span data-stu-id="7d42c-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="7d42c-123">Класс System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="7d42c-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="7d42c-124">System.Net.Connection.m\_WriteList поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="7d42c-125">Класс System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="7d42c-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="7d42c-126">System.Net.ConnectionGroup.m\_ConnectionList поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="7d42c-127">Класс System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="7d42c-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="7d42c-128">System.Net.CoreResponseData.m\_ResponseHeaders поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="7d42c-129">System.Net.CoreResponseData.m\_StatusCode поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="7d42c-130">System.Net.HttpWebRequest. \_AutoRedirects поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="7d42c-131">System.Net.HttpWebRequest. \_CoreResponse поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="7d42c-132">System.Net.HttpWebRequest. \_HttpResponse поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="7d42c-133">System.Net.ServicePoint.m\_ConnectionGroupList поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="7d42c-134">System.Net.ServicePointManager.s\_ServicePointTable поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="7d42c-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes поля</span><span class="sxs-lookup"><span data-stu-id="7d42c-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="7d42c-136">Класс System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="7d42c-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="7d42c-137">Класс System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="7d42c-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="7d42c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7d42c-138">See also</span></span>

[<span data-ttu-id="7d42c-139">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="7d42c-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
