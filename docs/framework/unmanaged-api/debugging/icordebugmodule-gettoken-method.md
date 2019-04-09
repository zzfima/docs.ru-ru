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
ms.openlocfilehash: c28182feff8e4b7d49b7d068da1496d44fa2f917
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150362"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="414af-102">Метод ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="414af-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="414af-103">Получает токен для записи в таблице для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="414af-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="414af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="414af-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="414af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="414af-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="414af-106">[out] Указатель на `mdModule` маркер, который ссылается на метаданные модуля.</span><span class="sxs-lookup"><span data-stu-id="414af-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="414af-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="414af-107">Remarks</span></span>  
 <span data-ttu-id="414af-108">Можно передать маркер [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), и [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейсы импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="414af-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="414af-109">Требования</span><span class="sxs-lookup"><span data-stu-id="414af-109">Requirements</span></span>  
 <span data-ttu-id="414af-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="414af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="414af-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="414af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="414af-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="414af-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="414af-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="414af-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="414af-114">См. также</span><span class="sxs-lookup"><span data-stu-id="414af-114">See also</span></span>

- [<span data-ttu-id="414af-115">Метаданные</span><span class="sxs-lookup"><span data-stu-id="414af-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
