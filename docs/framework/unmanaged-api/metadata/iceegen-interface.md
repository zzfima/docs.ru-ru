---
title: "Интерфейс ICeeGen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen
helpviewer_keywords: ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8342c79dd8b7452599af8d9782b0fbec5f83e964
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iceegen-interface"></a><span data-ttu-id="b7bb8-102">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b7bb8-102">ICeeGen Interface</span></span>
<span data-ttu-id="b7bb8-103">Предоставляет методы для динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="b7bb8-104">Этот интерфейс устарел и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7bb8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b7bb8-105">Methods</span></span>  
  
|<span data-ttu-id="b7bb8-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b7bb8-106">Method</span></span>|<span data-ttu-id="b7bb8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b7bb8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7bb8-108">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="b7bb8-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="b7bb8-109">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-109">Obsolete.</span></span> <span data-ttu-id="b7bb8-110">Добавляет инструкцию .reloc в базу кода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="b7bb8-111">Метод AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="b7bb8-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="b7bb8-112">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-112">Obsolete.</span></span> <span data-ttu-id="b7bb8-113">Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="b7bb8-114">Метод ComputePointer</span><span class="sxs-lookup"><span data-stu-id="b7bb8-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="b7bb8-115">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-115">Obsolete.</span></span> <span data-ttu-id="b7bb8-116">Определяет буфер для заданного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="b7bb8-117">Метод EmitString</span><span class="sxs-lookup"><span data-stu-id="b7bb8-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="b7bb8-118">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-118">Obsolete.</span></span> <span data-ttu-id="b7bb8-119">Выдает заданную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="b7bb8-120">Метод GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="b7bb8-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="b7bb8-121">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-121">Obsolete.</span></span> <span data-ttu-id="b7bb8-122">Создает файл базы кода, содержащий базу кода, загруженных в этот момент `ICeeGen`.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="b7bb8-123">Метод GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="b7bb8-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="b7bb8-124">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-124">Obsolete.</span></span> <span data-ttu-id="b7bb8-125">Создает образ в памяти в базе кода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="b7bb8-126">Метод GetIlSection</span><span class="sxs-lookup"><span data-stu-id="b7bb8-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="b7bb8-127">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-127">Obsolete.</span></span> <span data-ttu-id="b7bb8-128">Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="b7bb8-129">Метод GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="b7bb8-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="b7bb8-130">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-130">Obsolete.</span></span> <span data-ttu-id="b7bb8-131">Возвращает интерфейс, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="b7bb8-132">Метод GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="b7bb8-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="b7bb8-133">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-133">Obsolete.</span></span> <span data-ttu-id="b7bb8-134">Получает буфер соответствующего размера в указанный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="b7bb8-135">Метод GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="b7bb8-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="b7bb8-136">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-136">Obsolete.</span></span> <span data-ttu-id="b7bb8-137">Получает блок базы кода раздела.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="b7bb8-138">Метод GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="b7bb8-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="b7bb8-139">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-139">Obsolete.</span></span> <span data-ttu-id="b7bb8-140">Создает и возвращает раздел кода с помощью указанного имени и значения флагов.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="b7bb8-141">Метод GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="b7bb8-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="b7bb8-142">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-142">Obsolete.</span></span> <span data-ttu-id="b7bb8-143">Получает длину указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="b7bb8-144">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="b7bb8-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="b7bb8-145">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-145">Obsolete.</span></span> <span data-ttu-id="b7bb8-146">Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="b7bb8-147">Метод GetStringSection</span><span class="sxs-lookup"><span data-stu-id="b7bb8-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="b7bb8-148">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-148">Obsolete.</span></span> <span data-ttu-id="b7bb8-149">Возвращает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="b7bb8-150">Метод TruncateSection</span><span class="sxs-lookup"><span data-stu-id="b7bb8-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="b7bb8-151">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-151">Obsolete.</span></span> <span data-ttu-id="b7bb8-152">Усекает заданный раздел кода указанной длины.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7bb8-153">Требования</span><span class="sxs-lookup"><span data-stu-id="b7bb8-153">Requirements</span></span>  
 <span data-ttu-id="b7bb8-154">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7bb8-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7bb8-155">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7bb8-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7bb8-156">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7bb8-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7bb8-157">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7bb8-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bb8-158">См. также</span><span class="sxs-lookup"><span data-stu-id="b7bb8-158">See Also</span></span>  
 [<span data-ttu-id="b7bb8-159">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="b7bb8-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
