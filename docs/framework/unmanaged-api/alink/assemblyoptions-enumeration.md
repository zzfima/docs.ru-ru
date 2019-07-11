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
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742265"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="f64ba-102">Перечисление AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="f64ba-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="f64ba-103">Перечисляет параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="f64ba-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f64ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f64ba-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="fields"></a><span data-ttu-id="f64ba-105">Поля</span><span class="sxs-lookup"><span data-stu-id="f64ba-105">Fields</span></span>  
  
|<span data-ttu-id="f64ba-106">Поле</span><span class="sxs-lookup"><span data-stu-id="f64ba-106">Field</span></span>|<span data-ttu-id="f64ba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f64ba-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f64ba-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="f64ba-108">optAssemTitle</span></span>|<span data-ttu-id="f64ba-109">Строка — определяет название сборки.</span><span class="sxs-lookup"><span data-stu-id="f64ba-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="f64ba-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="f64ba-110">optAssemDescription</span></span>|<span data-ttu-id="f64ba-111">Строка — содержит описание сборки.</span><span class="sxs-lookup"><span data-stu-id="f64ba-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="f64ba-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="f64ba-112">optAssemConfig</span></span>|<span data-ttu-id="f64ba-113">Строка — содержит конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="f64ba-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="f64ba-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="f64ba-114">optAssemOS</span></span>|<span data-ttu-id="f64ba-115">Строка - кодировке: «dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion».</span><span class="sxs-lookup"><span data-stu-id="f64ba-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="f64ba-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="f64ba-116">optAssemProcessor</span></span>|<span data-ttu-id="f64ba-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="f64ba-117">ULONG</span></span>|  
|<span data-ttu-id="f64ba-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="f64ba-118">optAssemLocale</span></span>|<span data-ttu-id="f64ba-119">Строка — содержит языковой стандарт сборки.</span><span class="sxs-lookup"><span data-stu-id="f64ba-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="f64ba-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="f64ba-120">optAssemVersion</span></span>|<span data-ttu-id="f64ba-121">Строка - кодировке: «Основная.дополнительная.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="f64ba-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="f64ba-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="f64ba-122">optAssemCompany</span></span>|<span data-ttu-id="f64ba-123">Строка — содержит компании.</span><span class="sxs-lookup"><span data-stu-id="f64ba-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="f64ba-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="f64ba-124">optAssemProduct</span></span>|<span data-ttu-id="f64ba-125">Строка — содержит имя продукта.</span><span class="sxs-lookup"><span data-stu-id="f64ba-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="f64ba-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="f64ba-126">optAssemProductVersion</span></span>|<span data-ttu-id="f64ba-127">Строка (также известный как InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="f64ba-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="f64ba-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="f64ba-128">optAssemCopyright</span></span>|<span data-ttu-id="f64ba-129">Строка — содержит сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="f64ba-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="f64ba-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="f64ba-130">optAssemTrademark</span></span>|<span data-ttu-id="f64ba-131">Строка — содержит сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="f64ba-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="f64ba-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="f64ba-132">optAssemKeyFile</span></span>|<span data-ttu-id="f64ba-133">String (имя файла).</span><span class="sxs-lookup"><span data-stu-id="f64ba-133">String (file name).</span></span>|  
|<span data-ttu-id="f64ba-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="f64ba-134">optAssemKeyName</span></span>|<span data-ttu-id="f64ba-135">Строка (имя ключа).</span><span class="sxs-lookup"><span data-stu-id="f64ba-135">String (The key name).</span></span>|  
|<span data-ttu-id="f64ba-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="f64ba-136">optAssemAlgID</span></span>|<span data-ttu-id="f64ba-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="f64ba-137">ULONG</span></span>|  
|<span data-ttu-id="f64ba-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="f64ba-138">optAssemFlags</span></span>|<span data-ttu-id="f64ba-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="f64ba-139">ULONG</span></span>|  
|<span data-ttu-id="f64ba-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="f64ba-140">optAssemHalfSign</span></span>|<span data-ttu-id="f64ba-141">Bool (также известен как DelaySign).</span><span class="sxs-lookup"><span data-stu-id="f64ba-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="f64ba-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="f64ba-142">optAssemFileVersion</span></span>|<span data-ttu-id="f64ba-143">Строка - кодируется как «Основная.дополнительная.сборка.редакция»--так же, как ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="f64ba-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="f64ba-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="f64ba-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="f64ba-145">Строка - кодируется как «Основная.дополнительная.сборка.редакция».</span><span class="sxs-lookup"><span data-stu-id="f64ba-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="f64ba-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="f64ba-146">optLastAssemOption</span></span>|<span data-ttu-id="f64ba-147">Счетчик числа элементов.</span><span class="sxs-lookup"><span data-stu-id="f64ba-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f64ba-148">Требования</span><span class="sxs-lookup"><span data-stu-id="f64ba-148">Requirements</span></span>  
 <span data-ttu-id="f64ba-149">**Заголовок:** alink.h</span><span class="sxs-lookup"><span data-stu-id="f64ba-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="f64ba-150">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="f64ba-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64ba-151">См. также</span><span class="sxs-lookup"><span data-stu-id="f64ba-151">See also</span></span>

- [<span data-ttu-id="f64ba-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="f64ba-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
