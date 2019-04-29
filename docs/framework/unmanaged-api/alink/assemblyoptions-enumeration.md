---
title: Перечисление AssemblyOptions
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790108"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="dbac2-102">Перечисление AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="dbac2-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="dbac2-103">Перечисляет параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="dbac2-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbac2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbac2-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="dbac2-105">Поля</span><span class="sxs-lookup"><span data-stu-id="dbac2-105">Fields</span></span>  
  
|<span data-ttu-id="dbac2-106">Поле</span><span class="sxs-lookup"><span data-stu-id="dbac2-106">Field</span></span>|<span data-ttu-id="dbac2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dbac2-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dbac2-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="dbac2-108">optAssemTitle</span></span>|<span data-ttu-id="dbac2-109">Строка — определяет название сборки.</span><span class="sxs-lookup"><span data-stu-id="dbac2-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="dbac2-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="dbac2-110">optAssemDescription</span></span>|<span data-ttu-id="dbac2-111">Строка — содержит описание сборки.</span><span class="sxs-lookup"><span data-stu-id="dbac2-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="dbac2-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="dbac2-112">optAssemConfig</span></span>|<span data-ttu-id="dbac2-113">Строка — содержит конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="dbac2-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="dbac2-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="dbac2-114">optAssemOS</span></span>|<span data-ttu-id="dbac2-115">Строка - кодировке: «dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion».</span><span class="sxs-lookup"><span data-stu-id="dbac2-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="dbac2-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="dbac2-116">optAssemProcessor</span></span>|<span data-ttu-id="dbac2-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="dbac2-117">ULONG</span></span>|  
|<span data-ttu-id="dbac2-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="dbac2-118">optAssemLocale</span></span>|<span data-ttu-id="dbac2-119">Строка — содержит языковой стандарт сборки.</span><span class="sxs-lookup"><span data-stu-id="dbac2-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="dbac2-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="dbac2-120">optAssemVersion</span></span>|<span data-ttu-id="dbac2-121">Строка - кодировке: «Основная.дополнительная.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="dbac2-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="dbac2-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="dbac2-122">optAssemCompany</span></span>|<span data-ttu-id="dbac2-123">Строка — содержит компании.</span><span class="sxs-lookup"><span data-stu-id="dbac2-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="dbac2-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="dbac2-124">optAssemProduct</span></span>|<span data-ttu-id="dbac2-125">Строка — содержит имя продукта.</span><span class="sxs-lookup"><span data-stu-id="dbac2-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="dbac2-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="dbac2-126">optAssemProductVersion</span></span>|<span data-ttu-id="dbac2-127">Строка (также известный как InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="dbac2-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="dbac2-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="dbac2-128">optAssemCopyright</span></span>|<span data-ttu-id="dbac2-129">Строка — содержит сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="dbac2-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="dbac2-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="dbac2-130">optAssemTrademark</span></span>|<span data-ttu-id="dbac2-131">Строка — содержит сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="dbac2-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="dbac2-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="dbac2-132">optAssemKeyFile</span></span>|<span data-ttu-id="dbac2-133">String (имя файла).</span><span class="sxs-lookup"><span data-stu-id="dbac2-133">String (file name).</span></span>|  
|<span data-ttu-id="dbac2-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="dbac2-134">optAssemKeyName</span></span>|<span data-ttu-id="dbac2-135">Строка (имя ключа).</span><span class="sxs-lookup"><span data-stu-id="dbac2-135">String (The key name).</span></span>|  
|<span data-ttu-id="dbac2-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="dbac2-136">optAssemAlgID</span></span>|<span data-ttu-id="dbac2-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="dbac2-137">ULONG</span></span>|  
|<span data-ttu-id="dbac2-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="dbac2-138">optAssemFlags</span></span>|<span data-ttu-id="dbac2-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="dbac2-139">ULONG</span></span>|  
|<span data-ttu-id="dbac2-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="dbac2-140">optAssemHalfSign</span></span>|<span data-ttu-id="dbac2-141">Bool (также известен как DelaySign).</span><span class="sxs-lookup"><span data-stu-id="dbac2-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="dbac2-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="dbac2-142">optAssemFileVersion</span></span>|<span data-ttu-id="dbac2-143">Строка - кодируется как «Основная.дополнительная.сборка.редакция»--так же, как ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="dbac2-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="dbac2-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="dbac2-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="dbac2-145">Строка - кодируется как «Основная.дополнительная.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="dbac2-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="dbac2-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="dbac2-146">optLastAssemOption</span></span>|<span data-ttu-id="dbac2-147">Счетчик числа элементов.</span><span class="sxs-lookup"><span data-stu-id="dbac2-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbac2-148">Требования</span><span class="sxs-lookup"><span data-stu-id="dbac2-148">Requirements</span></span>  
 <span data-ttu-id="dbac2-149">**Заголовок:** alink.h</span><span class="sxs-lookup"><span data-stu-id="dbac2-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="dbac2-150">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="dbac2-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbac2-151">См. также</span><span class="sxs-lookup"><span data-stu-id="dbac2-151">See also</span></span>

- [<span data-ttu-id="dbac2-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="dbac2-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
