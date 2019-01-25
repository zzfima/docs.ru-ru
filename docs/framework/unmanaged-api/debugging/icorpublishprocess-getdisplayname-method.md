---
title: Метод ICorPublishProcess::GetDisplayName
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2d3624d130c005f9ed9109863b052e3272797ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496823"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="cf134-102">Метод ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="cf134-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="cf134-103">Возвращает полный путь к исполняемому файлу для процесса, который ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cf134-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf134-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf134-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf134-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf134-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cf134-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="cf134-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cf134-107">[out] Число расширенных символов, возвращаемых в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="cf134-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="cf134-108">[out] Массив для хранения имени, включая полный путь исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="cf134-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="cf134-109">Имя заканчивается нулевым байтом.</span><span class="sxs-lookup"><span data-stu-id="cf134-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf134-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cf134-110">Requirements</span></span>  
 <span data-ttu-id="cf134-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf134-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf134-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cf134-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cf134-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf134-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf134-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf134-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf134-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cf134-115">See also</span></span>
- [<span data-ttu-id="cf134-116">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="cf134-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
