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
ms.openlocfilehash: e3926a0d49b2db02cf52a3cc943b05edc4cc36a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406290"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="28529-102">Перечисление AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="28529-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="28529-103">Перечисляет параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="28529-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28529-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28529-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="28529-105">Поля</span><span class="sxs-lookup"><span data-stu-id="28529-105">Fields</span></span>  
  
|<span data-ttu-id="28529-106">Поле</span><span class="sxs-lookup"><span data-stu-id="28529-106">Field</span></span>|<span data-ttu-id="28529-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28529-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28529-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="28529-108">optAssemTitle</span></span>|<span data-ttu-id="28529-109">Строка — определяет название сборки.</span><span class="sxs-lookup"><span data-stu-id="28529-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="28529-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="28529-110">optAssemDescription</span></span>|<span data-ttu-id="28529-111">Строка — содержит описание сборки.</span><span class="sxs-lookup"><span data-stu-id="28529-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="28529-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="28529-112">optAssemConfig</span></span>|<span data-ttu-id="28529-113">Строка — содержит конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="28529-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="28529-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="28529-114">optAssemOS</span></span>|<span data-ttu-id="28529-115">Строка - кодировке: «dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion».</span><span class="sxs-lookup"><span data-stu-id="28529-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="28529-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="28529-116">optAssemProcessor</span></span>|<span data-ttu-id="28529-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="28529-117">ULONG</span></span>|  
|<span data-ttu-id="28529-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="28529-118">optAssemLocale</span></span>|<span data-ttu-id="28529-119">Строка — содержит языковой стандарт сборки.</span><span class="sxs-lookup"><span data-stu-id="28529-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="28529-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="28529-120">optAssemVersion</span></span>|<span data-ttu-id="28529-121">Строка - кодировке: «Основной_номер.дополнительный_номер.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="28529-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="28529-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="28529-122">optAssemCompany</span></span>|<span data-ttu-id="28529-123">Строка — содержит компании.</span><span class="sxs-lookup"><span data-stu-id="28529-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="28529-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="28529-124">optAssemProduct</span></span>|<span data-ttu-id="28529-125">Строка — содержит имя продукта.</span><span class="sxs-lookup"><span data-stu-id="28529-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="28529-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="28529-126">optAssemProductVersion</span></span>|<span data-ttu-id="28529-127">Строка (также известный как InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="28529-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="28529-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="28529-128">optAssemCopyright</span></span>|<span data-ttu-id="28529-129">Строка — содержит сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="28529-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="28529-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="28529-130">optAssemTrademark</span></span>|<span data-ttu-id="28529-131">Строка — содержит сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="28529-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="28529-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="28529-132">optAssemKeyFile</span></span>|<span data-ttu-id="28529-133">Строка (имя файла).</span><span class="sxs-lookup"><span data-stu-id="28529-133">String (file name).</span></span>|  
|<span data-ttu-id="28529-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="28529-134">optAssemKeyName</span></span>|<span data-ttu-id="28529-135">Строка (имя ключа).</span><span class="sxs-lookup"><span data-stu-id="28529-135">String (The key name).</span></span>|  
|<span data-ttu-id="28529-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="28529-136">optAssemAlgID</span></span>|<span data-ttu-id="28529-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="28529-137">ULONG</span></span>|  
|<span data-ttu-id="28529-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="28529-138">optAssemFlags</span></span>|<span data-ttu-id="28529-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="28529-139">ULONG</span></span>|  
|<span data-ttu-id="28529-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="28529-140">optAssemHalfSign</span></span>|<span data-ttu-id="28529-141">Значение типа bool (также называется DelaySign).</span><span class="sxs-lookup"><span data-stu-id="28529-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="28529-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="28529-142">optAssemFileVersion</span></span>|<span data-ttu-id="28529-143">Строка - кодируется как «Основной_номер.дополнительный_номер.сборка.редакция» — то же, что ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="28529-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="28529-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="28529-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="28529-145">Строка - кодируется как «Основной_номер.дополнительный_номер.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="28529-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="28529-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="28529-146">optLastAssemOption</span></span>|<span data-ttu-id="28529-147">Счетчик числа элементов.</span><span class="sxs-lookup"><span data-stu-id="28529-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28529-148">Требования</span><span class="sxs-lookup"><span data-stu-id="28529-148">Requirements</span></span>  
 <span data-ttu-id="28529-149">**Заголовок:** alink.h</span><span class="sxs-lookup"><span data-stu-id="28529-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="28529-150">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="28529-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28529-151">См. также</span><span class="sxs-lookup"><span data-stu-id="28529-151">See Also</span></span>  
 [<span data-ttu-id="28529-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="28529-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
