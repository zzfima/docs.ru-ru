---
title: Метод ICorDebugModule::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30097ff0cd92253897a366a5a18f305eddb06b5b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763528"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="d5477-102">Метод ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="d5477-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="d5477-103">Получает токен для записи в таблице для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d5477-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5477-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5477-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5477-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5477-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="d5477-106">[out] Указатель на `mdModule` маркер, который ссылается на метаданные модуля.</span><span class="sxs-lookup"><span data-stu-id="d5477-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5477-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5477-107">Remarks</span></span>  
 <span data-ttu-id="d5477-108">Можно передать маркер [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), и [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейсы импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="d5477-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5477-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d5477-109">Requirements</span></span>  
 <span data-ttu-id="d5477-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5477-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5477-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5477-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5477-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5477-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5477-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5477-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5477-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d5477-114">See also</span></span>

- [<span data-ttu-id="d5477-115">Метаданные</span><span class="sxs-lookup"><span data-stu-id="d5477-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
