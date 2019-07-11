---
title: Метод ICLRDataTarget::GetImageBase
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbb655d6ed0b9bd88c5eedf61a191401a805fb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738753"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="851c6-102">Метод ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="851c6-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="851c6-103">Получает базовый адрес памяти указанного изображения.</span><span class="sxs-lookup"><span data-stu-id="851c6-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="851c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="851c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="851c6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="851c6-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="851c6-106">[in] Имя файла изображения, включая его путь.</span><span class="sxs-lookup"><span data-stu-id="851c6-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="851c6-107">[out] Указатель на CLRDATA_ADDRESS, который хранит базового адреса образа.</span><span class="sxs-lookup"><span data-stu-id="851c6-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="851c6-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="851c6-108">Remarks</span></span>  
 <span data-ttu-id="851c6-109">Имя файла изображения может иметь или не иметь путь.</span><span class="sxs-lookup"><span data-stu-id="851c6-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="851c6-110">Если указан путь, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только на имя файла.</span><span class="sxs-lookup"><span data-stu-id="851c6-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="851c6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="851c6-111">Requirements</span></span>  
 <span data-ttu-id="851c6-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="851c6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="851c6-113">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="851c6-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="851c6-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="851c6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="851c6-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="851c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="851c6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="851c6-116">See also</span></span>

- [<span data-ttu-id="851c6-117">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="851c6-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
