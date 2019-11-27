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
ms.openlocfilehash: ed45e06297b77ea60304cdcfe1b08e97f9e4c085
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446588"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="da9fd-102">Перечисление AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="da9fd-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="da9fd-103">Перечисляет параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="da9fd-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da9fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da9fd-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="da9fd-105">Поля</span><span class="sxs-lookup"><span data-stu-id="da9fd-105">Fields</span></span>  
  
|<span data-ttu-id="da9fd-106">Поле</span><span class="sxs-lookup"><span data-stu-id="da9fd-106">Field</span></span>|<span data-ttu-id="da9fd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="da9fd-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="da9fd-108">оптассемтитле</span><span class="sxs-lookup"><span data-stu-id="da9fd-108">optAssemTitle</span></span>|<span data-ttu-id="da9fd-109">Строка — представляет заголовок сборки.</span><span class="sxs-lookup"><span data-stu-id="da9fd-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="da9fd-110">оптассемдескриптион</span><span class="sxs-lookup"><span data-stu-id="da9fd-110">optAssemDescription</span></span>|<span data-ttu-id="da9fd-111">Строка — содержит описание сборки.</span><span class="sxs-lookup"><span data-stu-id="da9fd-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="da9fd-112">оптассемконфиг</span><span class="sxs-lookup"><span data-stu-id="da9fd-112">optAssemConfig</span></span>|<span data-ttu-id="da9fd-113">Строка — содержит конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="da9fd-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="da9fd-114">оптассемос</span><span class="sxs-lookup"><span data-stu-id="da9fd-114">optAssemOS</span></span>|<span data-ttu-id="da9fd-115">Строка в кодировке: "Двосплатформид. Двосмажорверсион. Двосминорверсион".</span><span class="sxs-lookup"><span data-stu-id="da9fd-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="da9fd-116">оптассемпроцессор</span><span class="sxs-lookup"><span data-stu-id="da9fd-116">optAssemProcessor</span></span>|<span data-ttu-id="da9fd-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="da9fd-117">ULONG</span></span>|  
|<span data-ttu-id="da9fd-118">оптассемлокале</span><span class="sxs-lookup"><span data-stu-id="da9fd-118">optAssemLocale</span></span>|<span data-ttu-id="da9fd-119">Строка — содержит языковой стандарт сборки.</span><span class="sxs-lookup"><span data-stu-id="da9fd-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="da9fd-120">оптассемверсион</span><span class="sxs-lookup"><span data-stu-id="da9fd-120">optAssemVersion</span></span>|<span data-ttu-id="da9fd-121">Строка в кодировке: "основная. Дополнительная. сборка. Редакция".</span><span class="sxs-lookup"><span data-stu-id="da9fd-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="da9fd-122">оптассемкомпани</span><span class="sxs-lookup"><span data-stu-id="da9fd-122">optAssemCompany</span></span>|<span data-ttu-id="da9fd-123">Строка — содержит компанию.</span><span class="sxs-lookup"><span data-stu-id="da9fd-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="da9fd-124">оптассемпродукт</span><span class="sxs-lookup"><span data-stu-id="da9fd-124">optAssemProduct</span></span>|<span data-ttu-id="da9fd-125">Строка — содержит имя продукта.</span><span class="sxs-lookup"><span data-stu-id="da9fd-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="da9fd-126">оптассемпродуктверсион</span><span class="sxs-lookup"><span data-stu-id="da9fd-126">optAssemProductVersion</span></span>|<span data-ttu-id="da9fd-127">Строка (также известная как Информатионалверсион).</span><span class="sxs-lookup"><span data-stu-id="da9fd-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="da9fd-128">оптассемкопиригхт</span><span class="sxs-lookup"><span data-stu-id="da9fd-128">optAssemCopyright</span></span>|<span data-ttu-id="da9fd-129">Строка — содержит сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="da9fd-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="da9fd-130">оптассемтрадемарк</span><span class="sxs-lookup"><span data-stu-id="da9fd-130">optAssemTrademark</span></span>|<span data-ttu-id="da9fd-131">Строка — содержит сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="da9fd-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="da9fd-132">оптассемкэйфиле</span><span class="sxs-lookup"><span data-stu-id="da9fd-132">optAssemKeyFile</span></span>|<span data-ttu-id="da9fd-133">Строка (имя файла).</span><span class="sxs-lookup"><span data-stu-id="da9fd-133">String (file name).</span></span>|  
|<span data-ttu-id="da9fd-134">оптассемкэйнаме</span><span class="sxs-lookup"><span data-stu-id="da9fd-134">optAssemKeyName</span></span>|<span data-ttu-id="da9fd-135">Строка (имя ключа).</span><span class="sxs-lookup"><span data-stu-id="da9fd-135">String (The key name).</span></span>|  
|<span data-ttu-id="da9fd-136">оптассемалгид</span><span class="sxs-lookup"><span data-stu-id="da9fd-136">optAssemAlgID</span></span>|<span data-ttu-id="da9fd-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="da9fd-137">ULONG</span></span>|  
|<span data-ttu-id="da9fd-138">оптассемфлагс</span><span class="sxs-lookup"><span data-stu-id="da9fd-138">optAssemFlags</span></span>|<span data-ttu-id="da9fd-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="da9fd-139">ULONG</span></span>|  
|<span data-ttu-id="da9fd-140">оптассемхалфсигн</span><span class="sxs-lookup"><span data-stu-id="da9fd-140">optAssemHalfSign</span></span>|<span data-ttu-id="da9fd-141">Bool (также называется DelaySign).</span><span class="sxs-lookup"><span data-stu-id="da9fd-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="da9fd-142">оптассемфилеверсион</span><span class="sxs-lookup"><span data-stu-id="da9fd-142">optAssemFileVersion</span></span>|<span data-ttu-id="da9fd-143">Строка, закодированная как "основная. Дополнительная. сборка. Редакция"--то же, что и ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="da9fd-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="da9fd-144">оптассемсателлитевер</span><span class="sxs-lookup"><span data-stu-id="da9fd-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="da9fd-145">Строка, закодированная как "основная. Дополнительная. сборка. Редакция".</span><span class="sxs-lookup"><span data-stu-id="da9fd-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="da9fd-146">оптластассемоптион</span><span class="sxs-lookup"><span data-stu-id="da9fd-146">optLastAssemOption</span></span>|<span data-ttu-id="da9fd-147">Счетчик числа элементов.</span><span class="sxs-lookup"><span data-stu-id="da9fd-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da9fd-148">Требования</span><span class="sxs-lookup"><span data-stu-id="da9fd-148">Requirements</span></span>  
 <span data-ttu-id="da9fd-149">**Заголовок:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="da9fd-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="da9fd-150">**Библиотека**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="da9fd-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9fd-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="da9fd-151">See also</span></span>

- [<span data-ttu-id="da9fd-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="da9fd-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
