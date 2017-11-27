---
title: "Метод ICorPublishProcess::GetDisplayName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.GetDisplayName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bbaa05d767302bcd75303ec902a82e7992e1db3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="04a31-102">Метод ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="04a31-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="04a31-103">Получает полный путь к исполняемому файлу процесса ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="04a31-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04a31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04a31-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04a31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04a31-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="04a31-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="04a31-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="04a31-107">[out] Число расширенных символов, возвращаемых в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="04a31-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="04a31-108">[out] Массив для хранения имени, включая полный путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="04a31-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="04a31-109">Имя оканчивается символом null.</span><span class="sxs-lookup"><span data-stu-id="04a31-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04a31-110">Требования</span><span class="sxs-lookup"><span data-stu-id="04a31-110">Requirements</span></span>  
 <span data-ttu-id="04a31-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04a31-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04a31-112">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="04a31-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="04a31-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04a31-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04a31-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04a31-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a31-115">См. также</span><span class="sxs-lookup"><span data-stu-id="04a31-115">See Also</span></span>  
 [<span data-ttu-id="04a31-116">ICorPublishProcess-интерфейс</span><span class="sxs-lookup"><span data-stu-id="04a31-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
