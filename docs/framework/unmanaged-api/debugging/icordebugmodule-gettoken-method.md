---
title: "Метод ICorDebugModule::GetToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c06c4c8ac937864748cbac8872de9b3994db2464
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="4624d-102">Метод ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="4624d-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="4624d-103">Получает маркер для записи таблицы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="4624d-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4624d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4624d-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4624d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4624d-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="4624d-106">[out] Указатель на `mdModule` маркер, который ссылается на метаданные модуля.</span><span class="sxs-lookup"><span data-stu-id="4624d-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4624d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4624d-107">Remarks</span></span>  
 <span data-ttu-id="4624d-108">Можно передать токен [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), и [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейсы импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="4624d-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4624d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4624d-109">Requirements</span></span>  
 <span data-ttu-id="4624d-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4624d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4624d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4624d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4624d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4624d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4624d-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4624d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4624d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4624d-114">See Also</span></span>  
 [<span data-ttu-id="4624d-115">Метаданные</span><span class="sxs-lookup"><span data-stu-id="4624d-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
