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
ms.openlocfilehash: fcf0ab73c79a5fa116a89cdfcc2e73b17d9eabfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785495"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="1f8c8-102">Метод ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="1f8c8-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="1f8c8-103">Возвращает адрес базовой памяти указанного образа.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f8c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f8c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f8c8-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="1f8c8-106">окне Имя файла образа, включая его путь.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="1f8c8-107">заполняет Указатель на CLRDATA_ADDRESS, в котором хранится базовый адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f8c8-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="1f8c8-108">Remarks</span></span>  
 <span data-ttu-id="1f8c8-109">Имя файла изображения может содержать или не иметь пути.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="1f8c8-110">Если указан путь, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только с именем файла.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f8c8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1f8c8-111">Requirements</span></span>  
 <span data-ttu-id="1f8c8-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f8c8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f8c8-113">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="1f8c8-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1f8c8-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f8c8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f8c8-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f8c8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8c8-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f8c8-116">See also</span></span>

- [<span data-ttu-id="1f8c8-117">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="1f8c8-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
