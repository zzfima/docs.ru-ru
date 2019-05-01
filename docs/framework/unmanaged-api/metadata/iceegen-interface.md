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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050211"
---
# <a name="iceegen-interface"></a><span data-ttu-id="63475-102">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="63475-102">ICeeGen Interface</span></span>
<span data-ttu-id="63475-103">Предоставляет методы для динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="63475-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="63475-104">Этот интерфейс является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="63475-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63475-105">Методы</span><span class="sxs-lookup"><span data-stu-id="63475-105">Methods</span></span>  
  
|<span data-ttu-id="63475-106">Метод</span><span class="sxs-lookup"><span data-stu-id="63475-106">Method</span></span>|<span data-ttu-id="63475-107">Описание</span><span class="sxs-lookup"><span data-stu-id="63475-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63475-108">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="63475-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="63475-109">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-109">Obsolete.</span></span> <span data-ttu-id="63475-110">Добавляет инструкцию .reloc базы кода.</span><span class="sxs-lookup"><span data-stu-id="63475-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="63475-111">Метод AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="63475-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="63475-112">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-112">Obsolete.</span></span> <span data-ttu-id="63475-113">Создает буфер заданного размера для метода и возвращает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="63475-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="63475-114">Метод ComputePointer</span><span class="sxs-lookup"><span data-stu-id="63475-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="63475-115">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-115">Obsolete.</span></span> <span data-ttu-id="63475-116">Определяет буфер для заданного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="63475-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="63475-117">Метод EmitString</span><span class="sxs-lookup"><span data-stu-id="63475-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="63475-118">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-118">Obsolete.</span></span> <span data-ttu-id="63475-119">Создает указанную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="63475-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="63475-120">Метод GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="63475-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="63475-121">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-121">Obsolete.</span></span> <span data-ttu-id="63475-122">Создает файл базы кода, который содержит базу кода, загруженные в этот момент `ICeeGen`.</span><span class="sxs-lookup"><span data-stu-id="63475-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="63475-123">Метод GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="63475-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="63475-124">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-124">Obsolete.</span></span> <span data-ttu-id="63475-125">Формирует изображение в памяти для базы кода.</span><span class="sxs-lookup"><span data-stu-id="63475-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="63475-126">Метод GetIlSection</span><span class="sxs-lookup"><span data-stu-id="63475-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="63475-127">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-127">Obsolete.</span></span> <span data-ttu-id="63475-128">Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="63475-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="63475-129">Метод GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="63475-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="63475-130">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-130">Obsolete.</span></span> <span data-ttu-id="63475-131">Получает интерфейс, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="63475-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="63475-132">Метод GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="63475-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="63475-133">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-133">Obsolete.</span></span> <span data-ttu-id="63475-134">Получает буфер соответствующего размера в указанный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="63475-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="63475-135">Метод GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="63475-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="63475-136">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-136">Obsolete.</span></span> <span data-ttu-id="63475-137">Получает блок разделе базы кода.</span><span class="sxs-lookup"><span data-stu-id="63475-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="63475-138">Метод GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="63475-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="63475-139">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-139">Obsolete.</span></span> <span data-ttu-id="63475-140">Создает и возвращает раздел кода, используя указанные имя и значения флагов.</span><span class="sxs-lookup"><span data-stu-id="63475-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="63475-141">Метод GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="63475-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="63475-142">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-142">Obsolete.</span></span> <span data-ttu-id="63475-143">Получает длину указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="63475-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="63475-144">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="63475-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="63475-145">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-145">Obsolete.</span></span> <span data-ttu-id="63475-146">Получает строку, хранящуюся в указанный относительный виртуальный адрес.</span><span class="sxs-lookup"><span data-stu-id="63475-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="63475-147">Метод GetStringSection</span><span class="sxs-lookup"><span data-stu-id="63475-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="63475-148">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-148">Obsolete.</span></span> <span data-ttu-id="63475-149">Получает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="63475-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="63475-150">Метод TruncateSection</span><span class="sxs-lookup"><span data-stu-id="63475-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="63475-151">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="63475-151">Obsolete.</span></span> <span data-ttu-id="63475-152">Усекает заданный раздел кода указанной длины.</span><span class="sxs-lookup"><span data-stu-id="63475-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63475-153">Требования</span><span class="sxs-lookup"><span data-stu-id="63475-153">Requirements</span></span>  
 <span data-ttu-id="63475-154">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63475-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63475-155">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="63475-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63475-156">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63475-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63475-157">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63475-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63475-158">См. также</span><span class="sxs-lookup"><span data-stu-id="63475-158">See also</span></span>

- [<span data-ttu-id="63475-159">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="63475-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
