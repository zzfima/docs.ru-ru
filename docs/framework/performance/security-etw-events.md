---
title: "События безопасности (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e28eeabecfe0f1043328618f6e1be143f198a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="4d1e9-102">События безопасности (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="4d1e9-102">Security ETW Events</span></span>
<span data-ttu-id="4d1e9-103"><a name="top"></a> События безопасности создаются при проверке строгого имени и проверке Authenticode.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-103"><a name="top"></a> Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="4d1e9-104">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="4d1e9-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="4d1e9-105">События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="4d1e9-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="4d1e9-106">События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="4d1e9-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="4d1e9-107">События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="4d1e9-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="4d1e9-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="4d1e9-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="4d1e9-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="4d1e9-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="4d1e9-110">Keyword for raising the event</span></span>|<span data-ttu-id="4d1e9-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="4d1e9-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4d1e9-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="4d1e9-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="4d1e9-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="4d1e9-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="4d1e9-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4d1e9-115">Событие</span><span class="sxs-lookup"><span data-stu-id="4d1e9-115">Event</span></span>|<span data-ttu-id="4d1e9-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4d1e9-116">Event ID</span></span>|<span data-ttu-id="4d1e9-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="4d1e9-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="4d1e9-118">181</span><span class="sxs-lookup"><span data-stu-id="4d1e9-118">181</span></span>|<span data-ttu-id="4d1e9-119">Начало проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="4d1e9-120">182</span><span class="sxs-lookup"><span data-stu-id="4d1e9-120">182</span></span>|<span data-ttu-id="4d1e9-121">Окончание проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="4d1e9-122">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4d1e9-123">Имя поля</span><span class="sxs-lookup"><span data-stu-id="4d1e9-123">Field name</span></span>|<span data-ttu-id="4d1e9-124">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4d1e9-124">Data type</span></span>|<span data-ttu-id="4d1e9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="4d1e9-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4d1e9-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="4d1e9-126">VerificationFlags</span></span>|<span data-ttu-id="4d1e9-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4d1e9-127">win:UInt32</span></span>|<span data-ttu-id="4d1e9-128">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-128">The verification flags.</span></span>|  
|<span data-ttu-id="4d1e9-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="4d1e9-129">ErrorCode</span></span>|<span data-ttu-id="4d1e9-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4d1e9-130">win:UInt32</span></span>|<span data-ttu-id="4d1e9-131">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-131">The HResult error code.</span></span>|  
|<span data-ttu-id="4d1e9-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4d1e9-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="4d1e9-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4d1e9-133">win:UnicodeString</span></span>|<span data-ttu-id="4d1e9-134">Полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="4d1e9-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4d1e9-135">ClrInstanceID</span></span>|<span data-ttu-id="4d1e9-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4d1e9-136">win:UInt16</span></span>|<span data-ttu-id="4d1e9-137">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4d1e9-138">К началу</span><span class="sxs-lookup"><span data-stu-id="4d1e9-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="4d1e9-139">События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="4d1e9-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="4d1e9-140">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4d1e9-141">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="4d1e9-141">Keyword for raising the event</span></span>|<span data-ttu-id="4d1e9-142">Уровень</span><span class="sxs-lookup"><span data-stu-id="4d1e9-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4d1e9-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="4d1e9-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="4d1e9-144">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="4d1e9-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="4d1e9-145">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4d1e9-146">Событие</span><span class="sxs-lookup"><span data-stu-id="4d1e9-146">Event</span></span>|<span data-ttu-id="4d1e9-147">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4d1e9-147">Event ID</span></span>|<span data-ttu-id="4d1e9-148">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="4d1e9-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="4d1e9-149">183</span><span class="sxs-lookup"><span data-stu-id="4d1e9-149">183</span></span>|<span data-ttu-id="4d1e9-150">Начало проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="4d1e9-151">184</span><span class="sxs-lookup"><span data-stu-id="4d1e9-151">184</span></span>|<span data-ttu-id="4d1e9-152">Окончание проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="4d1e9-153">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4d1e9-154">Имя поля</span><span class="sxs-lookup"><span data-stu-id="4d1e9-154">Field name</span></span>|<span data-ttu-id="4d1e9-155">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4d1e9-155">Data type</span></span>|<span data-ttu-id="4d1e9-156">Описание</span><span class="sxs-lookup"><span data-stu-id="4d1e9-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4d1e9-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="4d1e9-157">VerificationFlags</span></span>|<span data-ttu-id="4d1e9-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4d1e9-158">win:UInt32</span></span>|<span data-ttu-id="4d1e9-159">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-159">The verification flags.</span></span>|  
|<span data-ttu-id="4d1e9-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="4d1e9-160">ErrorCode</span></span>|<span data-ttu-id="4d1e9-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4d1e9-161">win:UInt32</span></span>|<span data-ttu-id="4d1e9-162">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-162">The HResult error code.</span></span>|  
|<span data-ttu-id="4d1e9-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="4d1e9-163">ModulePath</span></span>|<span data-ttu-id="4d1e9-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4d1e9-164">win:UnicodeString</span></span>|<span data-ttu-id="4d1e9-165">Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-165">The module path.</span></span>|  
|<span data-ttu-id="4d1e9-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4d1e9-166">ClrInstanceID</span></span>|<span data-ttu-id="4d1e9-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4d1e9-167">win:UInt16</span></span>|<span data-ttu-id="4d1e9-168">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4d1e9-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d1e9-169">См. также</span><span class="sxs-lookup"><span data-stu-id="4d1e9-169">See Also</span></span>  
 [<span data-ttu-id="4d1e9-170">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="4d1e9-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
