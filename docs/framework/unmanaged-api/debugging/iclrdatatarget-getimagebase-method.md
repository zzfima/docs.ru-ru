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
ms.openlocfilehash: 91d893c0df13fbcb44c66df7f268cffdffb5fff6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488435"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="0fe1b-102">Метод ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="0fe1b-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="0fe1b-103">Получает базовый адрес памяти указанного изображения.</span><span class="sxs-lookup"><span data-stu-id="0fe1b-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fe1b-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fe1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fe1b-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="0fe1b-106">[in] Имя файла изображения, включая его путь.</span><span class="sxs-lookup"><span data-stu-id="0fe1b-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="0fe1b-107">[out] Указатель на CLRDATA_ADDRESS, который хранит базового адреса образа.</span><span class="sxs-lookup"><span data-stu-id="0fe1b-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fe1b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0fe1b-108">Remarks</span></span>  
 <span data-ttu-id="0fe1b-109">Имя файла изображения может иметь или не иметь путь.</span><span class="sxs-lookup"><span data-stu-id="0fe1b-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="0fe1b-110">Если указан путь, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только на имя файла.</span><span class="sxs-lookup"><span data-stu-id="0fe1b-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe1b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0fe1b-111">Requirements</span></span>  
 <span data-ttu-id="0fe1b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fe1b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe1b-113">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0fe1b-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0fe1b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fe1b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fe1b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe1b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0fe1b-116">See also</span></span>
- [<span data-ttu-id="0fe1b-117">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="0fe1b-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
