---
title: "Перечисление AssemblyOptions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="5d3a6-102">Перечисление AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="5d3a6-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="5d3a6-103">Перечисляет параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d3a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d3a6-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="5d3a6-105">Поля</span><span class="sxs-lookup"><span data-stu-id="5d3a6-105">Fields</span></span>  
  
|<span data-ttu-id="5d3a6-106">Поле</span><span class="sxs-lookup"><span data-stu-id="5d3a6-106">Field</span></span>|<span data-ttu-id="5d3a6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5d3a6-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5d3a6-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="5d3a6-108">optAssemTitle</span></span>|<span data-ttu-id="5d3a6-109">Строка — определяет название сборки.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="5d3a6-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="5d3a6-110">optAssemDescription</span></span>|<span data-ttu-id="5d3a6-111">Строка — содержит описание сборки.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="5d3a6-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="5d3a6-112">optAssemConfig</span></span>|<span data-ttu-id="5d3a6-113">Строка — содержит конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="5d3a6-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="5d3a6-114">optAssemOS</span></span>|<span data-ttu-id="5d3a6-115">Строка - кодировке: «dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion».</span><span class="sxs-lookup"><span data-stu-id="5d3a6-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="5d3a6-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="5d3a6-116">optAssemProcessor</span></span>|<span data-ttu-id="5d3a6-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="5d3a6-117">ULONG</span></span>|  
|<span data-ttu-id="5d3a6-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="5d3a6-118">optAssemLocale</span></span>|<span data-ttu-id="5d3a6-119">Строка — содержит языковой стандарт сборки.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="5d3a6-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="5d3a6-120">optAssemVersion</span></span>|<span data-ttu-id="5d3a6-121">Строка - кодировке: «Основной_номер.дополнительный_номер.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="5d3a6-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="5d3a6-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="5d3a6-122">optAssemCompany</span></span>|<span data-ttu-id="5d3a6-123">Строка — содержит компании.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="5d3a6-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="5d3a6-124">optAssemProduct</span></span>|<span data-ttu-id="5d3a6-125">Строка — содержит имя продукта.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="5d3a6-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="5d3a6-126">optAssemProductVersion</span></span>|<span data-ttu-id="5d3a6-127">Строка (также известный как InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="5d3a6-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="5d3a6-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="5d3a6-128">optAssemCopyright</span></span>|<span data-ttu-id="5d3a6-129">Строка — содержит сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="5d3a6-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="5d3a6-130">optAssemTrademark</span></span>|<span data-ttu-id="5d3a6-131">Строка — содержит сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="5d3a6-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="5d3a6-132">optAssemKeyFile</span></span>|<span data-ttu-id="5d3a6-133">Строка (имя файла).</span><span class="sxs-lookup"><span data-stu-id="5d3a6-133">String (file name).</span></span>|  
|<span data-ttu-id="5d3a6-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="5d3a6-134">optAssemKeyName</span></span>|<span data-ttu-id="5d3a6-135">Строка (имя ключа).</span><span class="sxs-lookup"><span data-stu-id="5d3a6-135">String (The key name).</span></span>|  
|<span data-ttu-id="5d3a6-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="5d3a6-136">optAssemAlgID</span></span>|<span data-ttu-id="5d3a6-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="5d3a6-137">ULONG</span></span>|  
|<span data-ttu-id="5d3a6-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="5d3a6-138">optAssemFlags</span></span>|<span data-ttu-id="5d3a6-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="5d3a6-139">ULONG</span></span>|  
|<span data-ttu-id="5d3a6-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="5d3a6-140">optAssemHalfSign</span></span>|<span data-ttu-id="5d3a6-141">Значение типа bool (также называется DelaySign).</span><span class="sxs-lookup"><span data-stu-id="5d3a6-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="5d3a6-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="5d3a6-142">optAssemFileVersion</span></span>|<span data-ttu-id="5d3a6-143">Строка - кодируется как «Основной_номер.дополнительный_номер.сборка.редакция» — то же, что ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="5d3a6-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="5d3a6-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="5d3a6-145">Строка - кодируется как «Основной_номер.дополнительный_номер.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="5d3a6-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="5d3a6-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="5d3a6-146">optLastAssemOption</span></span>|<span data-ttu-id="5d3a6-147">Счетчик числа элементов.</span><span class="sxs-lookup"><span data-stu-id="5d3a6-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d3a6-148">Требования</span><span class="sxs-lookup"><span data-stu-id="5d3a6-148">Requirements</span></span>  
 <span data-ttu-id="5d3a6-149">**Заголовок:** alink.h</span><span class="sxs-lookup"><span data-stu-id="5d3a6-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="5d3a6-150">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="5d3a6-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3a6-151">См. также</span><span class="sxs-lookup"><span data-stu-id="5d3a6-151">See Also</span></span>  
 [<span data-ttu-id="5d3a6-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="5d3a6-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
