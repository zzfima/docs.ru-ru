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
ms.openlocfilehash: 4f87724bda78c1948ae7e1ddfa3d586fe5b7e14e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575740"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="c7896-102">Метод ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="c7896-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="c7896-103">Получает токен для записи в таблице для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="c7896-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7896-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7896-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7896-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7896-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="c7896-106">[out] Указатель на `mdModule` маркер, который ссылается на метаданные модуля.</span><span class="sxs-lookup"><span data-stu-id="c7896-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7896-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7896-107">Remarks</span></span>  
 <span data-ttu-id="c7896-108">Можно передать маркер [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), и [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейсы импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="c7896-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7896-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c7896-109">Requirements</span></span>  
 <span data-ttu-id="c7896-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7896-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7896-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7896-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7896-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7896-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7896-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7896-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7896-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c7896-114">See also</span></span>
- [<span data-ttu-id="c7896-115">Метаданные</span><span class="sxs-lookup"><span data-stu-id="c7896-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
