---
title: Интерфейс ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176128"
---
# <a name="iceegen-interface"></a><span data-ttu-id="04e0a-102">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="04e0a-102">ICeeGen Interface</span></span>
<span data-ttu-id="04e0a-103">Предоставляет методы для динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="04e0a-104">Этот интерфейс является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="04e0a-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04e0a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="04e0a-105">Methods</span></span>  
  
|<span data-ttu-id="04e0a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="04e0a-106">Method</span></span>|<span data-ttu-id="04e0a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="04e0a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04e0a-108">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="04e0a-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="04e0a-109">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-109">Obsolete.</span></span> <span data-ttu-id="04e0a-110">Добавляет инструкцию .reloc базы кода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="04e0a-111">Метод AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="04e0a-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="04e0a-112">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-112">Obsolete.</span></span> <span data-ttu-id="04e0a-113">Создает буфер заданного размера для метода и возвращает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="04e0a-114">Метод ComputePointer</span><span class="sxs-lookup"><span data-stu-id="04e0a-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="04e0a-115">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-115">Obsolete.</span></span> <span data-ttu-id="04e0a-116">Определяет буфер для заданного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="04e0a-117">Метод EmitString</span><span class="sxs-lookup"><span data-stu-id="04e0a-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="04e0a-118">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-118">Obsolete.</span></span> <span data-ttu-id="04e0a-119">Создает указанную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="04e0a-120">Метод GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="04e0a-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="04e0a-121">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-121">Obsolete.</span></span> <span data-ttu-id="04e0a-122">Создает файл базы кода, который содержит базу кода, загруженные в этот момент `ICeeGen`.</span><span class="sxs-lookup"><span data-stu-id="04e0a-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="04e0a-123">Метод GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="04e0a-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="04e0a-124">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-124">Obsolete.</span></span> <span data-ttu-id="04e0a-125">Формирует изображение в памяти для базы кода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="04e0a-126">Метод GetIlSection</span><span class="sxs-lookup"><span data-stu-id="04e0a-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="04e0a-127">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-127">Obsolete.</span></span> <span data-ttu-id="04e0a-128">Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="04e0a-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="04e0a-129">Метод GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="04e0a-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="04e0a-130">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-130">Obsolete.</span></span> <span data-ttu-id="04e0a-131">Получает интерфейс, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="04e0a-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="04e0a-132">Метод GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="04e0a-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="04e0a-133">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-133">Obsolete.</span></span> <span data-ttu-id="04e0a-134">Получает буфер соответствующего размера в указанный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="04e0a-135">Метод GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="04e0a-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="04e0a-136">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-136">Obsolete.</span></span> <span data-ttu-id="04e0a-137">Получает блок разделе базы кода.</span><span class="sxs-lookup"><span data-stu-id="04e0a-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="04e0a-138">Метод GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="04e0a-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="04e0a-139">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-139">Obsolete.</span></span> <span data-ttu-id="04e0a-140">Создает и возвращает раздел кода, используя указанные имя и значения флагов.</span><span class="sxs-lookup"><span data-stu-id="04e0a-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="04e0a-141">Метод GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="04e0a-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="04e0a-142">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-142">Obsolete.</span></span> <span data-ttu-id="04e0a-143">Получает длину указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="04e0a-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="04e0a-144">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="04e0a-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="04e0a-145">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-145">Obsolete.</span></span> <span data-ttu-id="04e0a-146">Получает строку, хранящуюся в указанный относительный виртуальный адрес.</span><span class="sxs-lookup"><span data-stu-id="04e0a-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="04e0a-147">Метод GetStringSection</span><span class="sxs-lookup"><span data-stu-id="04e0a-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="04e0a-148">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-148">Obsolete.</span></span> <span data-ttu-id="04e0a-149">Получает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="04e0a-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="04e0a-150">Метод TruncateSection</span><span class="sxs-lookup"><span data-stu-id="04e0a-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="04e0a-151">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="04e0a-151">Obsolete.</span></span> <span data-ttu-id="04e0a-152">Усекает заданный раздел кода указанной длины.</span><span class="sxs-lookup"><span data-stu-id="04e0a-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04e0a-153">Требования</span><span class="sxs-lookup"><span data-stu-id="04e0a-153">Requirements</span></span>  
 <span data-ttu-id="04e0a-154">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04e0a-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04e0a-155">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="04e0a-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04e0a-156">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04e0a-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="04e0a-157">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="04e0a-157">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04e0a-158">См. также</span><span class="sxs-lookup"><span data-stu-id="04e0a-158">See also</span></span>

- [<span data-ttu-id="04e0a-159">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="04e0a-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
