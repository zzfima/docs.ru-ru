---
title: События безопасности (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715942"
---
# <a name="security-etw-events"></a><span data-ttu-id="180ef-102">События безопасности (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="180ef-102">Security ETW Events</span></span>

<span data-ttu-id="180ef-103">События безопасности создаются при проверке строгого имени и проверке Authenticode.</span><span class="sxs-lookup"><span data-stu-id="180ef-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="180ef-104">События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="180ef-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="180ef-105">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="180ef-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="180ef-106">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="180ef-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="180ef-107">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="180ef-107">Keyword for raising the event</span></span>|<span data-ttu-id="180ef-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="180ef-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="180ef-109">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="180ef-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="180ef-110">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="180ef-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="180ef-111">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="180ef-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="180ef-112">Event</span><span class="sxs-lookup"><span data-stu-id="180ef-112">Event</span></span>|<span data-ttu-id="180ef-113">Код события</span><span class="sxs-lookup"><span data-stu-id="180ef-113">Event ID</span></span>|<span data-ttu-id="180ef-114">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="180ef-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="180ef-115">181</span><span class="sxs-lookup"><span data-stu-id="180ef-115">181</span></span>|<span data-ttu-id="180ef-116">Начало проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="180ef-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="180ef-117">182</span><span class="sxs-lookup"><span data-stu-id="180ef-117">182</span></span>|<span data-ttu-id="180ef-118">Окончание проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="180ef-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="180ef-119">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="180ef-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="180ef-120">Имя поля</span><span class="sxs-lookup"><span data-stu-id="180ef-120">Field name</span></span>|<span data-ttu-id="180ef-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="180ef-121">Data type</span></span>|<span data-ttu-id="180ef-122">Описание</span><span class="sxs-lookup"><span data-stu-id="180ef-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="180ef-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="180ef-123">VerificationFlags</span></span>|<span data-ttu-id="180ef-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="180ef-124">win:UInt32</span></span>|<span data-ttu-id="180ef-125">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="180ef-125">The verification flags.</span></span>|  
|<span data-ttu-id="180ef-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="180ef-126">ErrorCode</span></span>|<span data-ttu-id="180ef-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="180ef-127">win:UInt32</span></span>|<span data-ttu-id="180ef-128">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="180ef-128">The HResult error code.</span></span>|  
|<span data-ttu-id="180ef-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="180ef-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="180ef-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="180ef-130">win:UnicodeString</span></span>|<span data-ttu-id="180ef-131">Полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="180ef-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="180ef-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="180ef-132">ClrInstanceID</span></span>|<span data-ttu-id="180ef-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="180ef-133">win:UInt16</span></span>|<span data-ttu-id="180ef-134">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="180ef-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="180ef-135">События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="180ef-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="180ef-136">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="180ef-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="180ef-137">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="180ef-137">Keyword for raising the event</span></span>|<span data-ttu-id="180ef-138">Уровень</span><span class="sxs-lookup"><span data-stu-id="180ef-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="180ef-139">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="180ef-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="180ef-140">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="180ef-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="180ef-141">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="180ef-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="180ef-142">Event</span><span class="sxs-lookup"><span data-stu-id="180ef-142">Event</span></span>|<span data-ttu-id="180ef-143">Код события</span><span class="sxs-lookup"><span data-stu-id="180ef-143">Event ID</span></span>|<span data-ttu-id="180ef-144">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="180ef-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="180ef-145">183</span><span class="sxs-lookup"><span data-stu-id="180ef-145">183</span></span>|<span data-ttu-id="180ef-146">Начало проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="180ef-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="180ef-147">184</span><span class="sxs-lookup"><span data-stu-id="180ef-147">184</span></span>|<span data-ttu-id="180ef-148">Окончание проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="180ef-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="180ef-149">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="180ef-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="180ef-150">Имя поля</span><span class="sxs-lookup"><span data-stu-id="180ef-150">Field name</span></span>|<span data-ttu-id="180ef-151">Тип данных</span><span class="sxs-lookup"><span data-stu-id="180ef-151">Data type</span></span>|<span data-ttu-id="180ef-152">Описание</span><span class="sxs-lookup"><span data-stu-id="180ef-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="180ef-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="180ef-153">VerificationFlags</span></span>|<span data-ttu-id="180ef-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="180ef-154">win:UInt32</span></span>|<span data-ttu-id="180ef-155">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="180ef-155">The verification flags.</span></span>|  
|<span data-ttu-id="180ef-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="180ef-156">ErrorCode</span></span>|<span data-ttu-id="180ef-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="180ef-157">win:UInt32</span></span>|<span data-ttu-id="180ef-158">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="180ef-158">The HResult error code.</span></span>|  
|<span data-ttu-id="180ef-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="180ef-159">ModulePath</span></span>|<span data-ttu-id="180ef-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="180ef-160">win:UnicodeString</span></span>|<span data-ttu-id="180ef-161">Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="180ef-161">The module path.</span></span>|  
|<span data-ttu-id="180ef-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="180ef-162">ClrInstanceID</span></span>|<span data-ttu-id="180ef-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="180ef-163">win:UInt16</span></span>|<span data-ttu-id="180ef-164">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="180ef-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="180ef-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="180ef-165">See also</span></span>

- [<span data-ttu-id="180ef-166">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="180ef-166">CLR ETW Events</span></span>](clr-etw-events.md)
