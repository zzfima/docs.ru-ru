---
title: Метод ICorDebugAppDomain::GetModuleFromMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48249bb634c301b7fda2c360c3b793e9206a759a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737903"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="1aa6d-102">Метод ICorDebugAppDomain::GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="1aa6d-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="1aa6d-103">Возвращает модуль, соответствующий данному интерфейсу метаданных.</span><span class="sxs-lookup"><span data-stu-id="1aa6d-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1aa6d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1aa6d-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="1aa6d-106">[in] Указатель на объект, который является одним из [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="1aa6d-106">[in] A pointer to an object that is one of the [Metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="1aa6d-107">[out] Указатель на адрес объекта ICorDebugModule, который представляет модуль, соответствующий данному интерфейсу метаданных.</span><span class="sxs-lookup"><span data-stu-id="1aa6d-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa6d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1aa6d-108">Requirements</span></span>  
 <span data-ttu-id="1aa6d-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa6d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa6d-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1aa6d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1aa6d-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aa6d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aa6d-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa6d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
