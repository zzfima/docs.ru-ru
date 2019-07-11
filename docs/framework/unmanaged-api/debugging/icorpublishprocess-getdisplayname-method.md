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
ms.openlocfilehash: 354e1b0dad942534068d5fb07071ed4ac695fb49
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764888"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="1c531-102">Метод ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="1c531-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="1c531-103">Возвращает полный путь к исполняемому файлу для процесса, который ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1c531-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c531-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c531-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c531-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c531-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1c531-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="1c531-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1c531-107">[out] Число расширенных символов, возвращаемых в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="1c531-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="1c531-108">[out] Массив для хранения имени, включая полный путь исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="1c531-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="1c531-109">Имя заканчивается нулевым байтом.</span><span class="sxs-lookup"><span data-stu-id="1c531-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c531-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1c531-110">Requirements</span></span>  
 <span data-ttu-id="1c531-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c531-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c531-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1c531-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1c531-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c531-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c531-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c531-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c531-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1c531-115">See also</span></span>

- [<span data-ttu-id="1c531-116">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="1c531-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
