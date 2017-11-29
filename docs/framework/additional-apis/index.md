---
title: "Дополнительные библиотеки классов и интерфейсы API"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3bb7a7c53cbca8bbd4026b46ce59589cef22382
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="a76aa-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="a76aa-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="a76aa-103">Платформа .NET Framework постоянно развивается. С целью совершенствования кроссплатформенной разработки и оперативного предоставления новых функциональных возможностей нашим клиентам мы выпускаем новые возможности в виде внештатных выпусков.</span><span class="sxs-lookup"><span data-stu-id="a76aa-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="a76aa-104">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="a76aa-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="a76aa-105">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a76aa-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="a76aa-106">Например <xref:System.Text.CodePagesEncodingProvider> класса делает доступными для приложений UWP, разработанных с помощью .NET Framework кодировок кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="a76aa-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="a76aa-107">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="a76aa-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="a76aa-108">Встроенные проекты</span><span class="sxs-lookup"><span data-stu-id="a76aa-108">OOB projects</span></span>
  
| <span data-ttu-id="a76aa-109">Проект</span><span class="sxs-lookup"><span data-stu-id="a76aa-109">Project</span></span> | <span data-ttu-id="a76aa-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a76aa-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="a76aa-111">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="a76aa-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="a76aa-112">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="a76aa-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="a76aa-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="a76aa-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="a76aa-114">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="a76aa-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="a76aa-115">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="a76aa-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="a76aa-116">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="a76aa-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="a76aa-117">Проект</span><span class="sxs-lookup"><span data-stu-id="a76aa-117">Project</span></span> | <span data-ttu-id="a76aa-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a76aa-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="a76aa-119">Расширяет <xref:System.Text.EncodingProvider> класса, чтобы сделать доступными для приложений, предназначенных для универсальной платформы Windows кодировок кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="a76aa-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="a76aa-120">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="a76aa-120">Private APIs</span></span>  

<span data-ttu-id="a76aa-121">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="a76aa-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="a76aa-122">Имя API</span><span class="sxs-lookup"><span data-stu-id="a76aa-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="a76aa-123">Класс System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="a76aa-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="a76aa-124">System.Net.Connection.m\_WriteList поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="a76aa-125">Класс System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="a76aa-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="a76aa-126">System.Net.ConnectionGroup.m\_ConnectionList поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="a76aa-127">System.Net.HttpWebRequest. \_HttpResponse поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-127">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="a76aa-128">System.Net.HttpWebRequest. \_AutoRedirects поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-128">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="a76aa-129">System.Net.ServicePoint.m\_ConnectionGroupList поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-129">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="a76aa-130">System.Net.ServicePointManager.s\_ServicePointTable поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-130">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="a76aa-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes поля</span><span class="sxs-lookup"><span data-stu-id="a76aa-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="a76aa-132">Класс System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="a76aa-132">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="a76aa-133">Класс System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="a76aa-133">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="a76aa-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a76aa-134">See also</span></span>

[<span data-ttu-id="a76aa-135">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="a76aa-135">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
