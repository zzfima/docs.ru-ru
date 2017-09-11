---
title: "Дополнительные библиотеки классов и интерфейсы API | Документы Майкрософт"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: b53b8acc2a6c56db6a9d8a9b7c685a2d400a53e1
ms.openlocfilehash: 34815268b707aa70d174a1bbc04c32276db8412d
ms.contentlocale: ru-ru
ms.lasthandoff: 05/02/2017

---

# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="911c9-102">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="911c9-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="911c9-103">Платформа .NET Framework постоянно развивается. С целью совершенствования кроссплатформенной разработки и оперативного предоставления новых функциональных возможностей нашим клиентам мы выпускаем новые возможности в виде внештатных выпусков.</span><span class="sxs-lookup"><span data-stu-id="911c9-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="911c9-104">В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.</span><span class="sxs-lookup"><span data-stu-id="911c9-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="911c9-105">Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="911c9-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="911c9-106">Например, благодаря классу <xref:System.Text.CodePagesEncodingProvider> кодировки кодовых страниц становятся доступными для приложений UWP, разработанных с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="911c9-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="911c9-107">В этой статье эти библиотеки перечислены тоже.</span><span class="sxs-lookup"><span data-stu-id="911c9-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="911c9-108">Встроенные проекты</span><span class="sxs-lookup"><span data-stu-id="911c9-108">OOB projects</span></span>
  
| <span data-ttu-id="911c9-109">Проект</span><span class="sxs-lookup"><span data-stu-id="911c9-109">Project</span></span> | <span data-ttu-id="911c9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="911c9-110">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="911c9-111"><xref:System.Collections.Immutable></span><span class="sxs-lookup"><span data-stu-id="911c9-111"><xref:System.Collections.Immutable></span></span> | <span data-ttu-id="911c9-112">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="911c9-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <span data-ttu-id="911c9-113"><xref:System.Net.Http.WinHttpHandler></span><span class="sxs-lookup"><span data-stu-id="911c9-113"><xref:System.Net.Http.WinHttpHandler></span></span> | <span data-ttu-id="911c9-114">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="911c9-114">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="911c9-115">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="911c9-115">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="911c9-116">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="911c9-116">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <span data-ttu-id="911c9-117"><xref:System.Threading.Tasks.Dataflow></span><span class="sxs-lookup"><span data-stu-id="911c9-117"><xref:System.Threading.Tasks.Dataflow></span></span> | <span data-ttu-id="911c9-118">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="911c9-118">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="911c9-119">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="911c9-119">Platform-specific libraries</span></span>
  
| <span data-ttu-id="911c9-120">Проект</span><span class="sxs-lookup"><span data-stu-id="911c9-120">Project</span></span> | <span data-ttu-id="911c9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="911c9-121">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="911c9-122"><xref:System.Text.CodePagesEncodingProvider></span><span class="sxs-lookup"><span data-stu-id="911c9-122"><xref:System.Text.CodePagesEncodingProvider></span></span> | <span data-ttu-id="911c9-123">Расширяет класс <xref:System.Text.EncodingProvider>, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальной платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="911c9-123">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="911c9-124">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="911c9-124">Private APIs</span></span>  

<span data-ttu-id="911c9-125">Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="911c9-125">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="911c9-126">Имя API</span><span class="sxs-lookup"><span data-stu-id="911c9-126">API Name</span></span> |  
| -------- |  
| [<span data-ttu-id="911c9-127">s_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="911c9-127">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |  
| [<span data-ttu-id="911c9-128">Класс DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="911c9-128">DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |  
| [<span data-ttu-id="911c9-129">Класс DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="911c9-129">DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |  
  
## <a name="see-also"></a><span data-ttu-id="911c9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="911c9-130">See also</span></span>

[<span data-ttu-id="911c9-131">.NET Framework и отдельные выпуски</span><span class="sxs-lookup"><span data-stu-id="911c9-131">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)

