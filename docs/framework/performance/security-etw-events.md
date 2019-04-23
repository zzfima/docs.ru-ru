---
title: События безопасности (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a19dce496423883e5fed62375c6db8ed5efdb1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134034"
---
# <a name="security-etw-events"></a><span data-ttu-id="437ec-102">События безопасности (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="437ec-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="437ec-103">События безопасности создаются при проверке строгого имени и проверке Authenticode.</span><span class="sxs-lookup"><span data-stu-id="437ec-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="437ec-104">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="437ec-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="437ec-105">События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="437ec-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="437ec-106">События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="437ec-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="437ec-107">События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="437ec-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="437ec-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="437ec-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="437ec-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="437ec-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="437ec-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="437ec-110">Keyword for raising the event</span></span>|<span data-ttu-id="437ec-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="437ec-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="437ec-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="437ec-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="437ec-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="437ec-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="437ec-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="437ec-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="437ec-115">событие</span><span class="sxs-lookup"><span data-stu-id="437ec-115">Event</span></span>|<span data-ttu-id="437ec-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="437ec-116">Event ID</span></span>|<span data-ttu-id="437ec-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="437ec-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="437ec-118">181</span><span class="sxs-lookup"><span data-stu-id="437ec-118">181</span></span>|<span data-ttu-id="437ec-119">Начало проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="437ec-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="437ec-120">182</span><span class="sxs-lookup"><span data-stu-id="437ec-120">182</span></span>|<span data-ttu-id="437ec-121">Окончание проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="437ec-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="437ec-122">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="437ec-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="437ec-123">Имя поля</span><span class="sxs-lookup"><span data-stu-id="437ec-123">Field name</span></span>|<span data-ttu-id="437ec-124">Тип данных</span><span class="sxs-lookup"><span data-stu-id="437ec-124">Data type</span></span>|<span data-ttu-id="437ec-125">Описание</span><span class="sxs-lookup"><span data-stu-id="437ec-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="437ec-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="437ec-126">VerificationFlags</span></span>|<span data-ttu-id="437ec-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="437ec-127">win:UInt32</span></span>|<span data-ttu-id="437ec-128">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="437ec-128">The verification flags.</span></span>|  
|<span data-ttu-id="437ec-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="437ec-129">ErrorCode</span></span>|<span data-ttu-id="437ec-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="437ec-130">win:UInt32</span></span>|<span data-ttu-id="437ec-131">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="437ec-131">The HResult error code.</span></span>|  
|<span data-ttu-id="437ec-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="437ec-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="437ec-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="437ec-133">win:UnicodeString</span></span>|<span data-ttu-id="437ec-134">Полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="437ec-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="437ec-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="437ec-135">ClrInstanceID</span></span>|<span data-ttu-id="437ec-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="437ec-136">win:UInt16</span></span>|<span data-ttu-id="437ec-137">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="437ec-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="437ec-138">К началу</span><span class="sxs-lookup"><span data-stu-id="437ec-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="437ec-139">События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="437ec-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="437ec-140">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="437ec-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="437ec-141">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="437ec-141">Keyword for raising the event</span></span>|<span data-ttu-id="437ec-142">Уровень</span><span class="sxs-lookup"><span data-stu-id="437ec-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="437ec-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="437ec-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="437ec-144">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="437ec-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="437ec-145">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="437ec-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="437ec-146">событие</span><span class="sxs-lookup"><span data-stu-id="437ec-146">Event</span></span>|<span data-ttu-id="437ec-147">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="437ec-147">Event ID</span></span>|<span data-ttu-id="437ec-148">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="437ec-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="437ec-149">183</span><span class="sxs-lookup"><span data-stu-id="437ec-149">183</span></span>|<span data-ttu-id="437ec-150">Начало проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="437ec-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="437ec-151">184</span><span class="sxs-lookup"><span data-stu-id="437ec-151">184</span></span>|<span data-ttu-id="437ec-152">Окончание проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="437ec-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="437ec-153">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="437ec-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="437ec-154">Имя поля</span><span class="sxs-lookup"><span data-stu-id="437ec-154">Field name</span></span>|<span data-ttu-id="437ec-155">Тип данных</span><span class="sxs-lookup"><span data-stu-id="437ec-155">Data type</span></span>|<span data-ttu-id="437ec-156">Описание</span><span class="sxs-lookup"><span data-stu-id="437ec-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="437ec-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="437ec-157">VerificationFlags</span></span>|<span data-ttu-id="437ec-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="437ec-158">win:UInt32</span></span>|<span data-ttu-id="437ec-159">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="437ec-159">The verification flags.</span></span>|  
|<span data-ttu-id="437ec-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="437ec-160">ErrorCode</span></span>|<span data-ttu-id="437ec-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="437ec-161">win:UInt32</span></span>|<span data-ttu-id="437ec-162">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="437ec-162">The HResult error code.</span></span>|  
|<span data-ttu-id="437ec-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="437ec-163">ModulePath</span></span>|<span data-ttu-id="437ec-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="437ec-164">win:UnicodeString</span></span>|<span data-ttu-id="437ec-165">Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="437ec-165">The module path.</span></span>|  
|<span data-ttu-id="437ec-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="437ec-166">ClrInstanceID</span></span>|<span data-ttu-id="437ec-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="437ec-167">win:UInt16</span></span>|<span data-ttu-id="437ec-168">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="437ec-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="437ec-169">См. также</span><span class="sxs-lookup"><span data-stu-id="437ec-169">See also</span></span>

- [<span data-ttu-id="437ec-170">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="437ec-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
