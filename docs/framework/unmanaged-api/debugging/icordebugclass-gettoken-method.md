---
title: Метод ICorDebugClass::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4f33bb15a351be5fe8318dcc3339d429dec039e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183707"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="b0310-102">Метод ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="b0310-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="b0310-103">Получает `TypeDef` токен метаданных, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="b0310-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0310-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0310-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0310-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0310-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="b0310-106">[out] Указатель на `mdTypeDef` маркер, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="b0310-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0310-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b0310-107">Requirements</span></span>  
 <span data-ttu-id="b0310-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0310-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0310-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0310-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0310-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0310-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b0310-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b0310-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0310-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b0310-112">See also</span></span>

- [<span data-ttu-id="b0310-113">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="b0310-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
