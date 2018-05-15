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
ms.openlocfilehash: 9a79133b117f3a718dd84af6c2144a6098bc79f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="c63a3-102">Метод ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="c63a3-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="c63a3-103">Получает базовый адрес памяти заданного образа.</span><span class="sxs-lookup"><span data-stu-id="c63a3-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c63a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c63a3-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c63a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c63a3-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="c63a3-106">[in] Имя файла изображения, включая путь к нему.</span><span class="sxs-lookup"><span data-stu-id="c63a3-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="c63a3-107">[out] Указатель на CLRDATA_ADDRESS, в которой хранятся базового адреса образа.</span><span class="sxs-lookup"><span data-stu-id="c63a3-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c63a3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c63a3-108">Remarks</span></span>  
 <span data-ttu-id="c63a3-109">Имя файла изображения может или не может иметь путь.</span><span class="sxs-lookup"><span data-stu-id="c63a3-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="c63a3-110">Если путь указан, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только по имени файла.</span><span class="sxs-lookup"><span data-stu-id="c63a3-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c63a3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c63a3-111">Requirements</span></span>  
 <span data-ttu-id="c63a3-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c63a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c63a3-113">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c63a3-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c63a3-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c63a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c63a3-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c63a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63a3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c63a3-116">See Also</span></span>  
 [<span data-ttu-id="c63a3-117">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="c63a3-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
