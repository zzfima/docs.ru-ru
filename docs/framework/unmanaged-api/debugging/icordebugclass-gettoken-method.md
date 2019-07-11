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
ms.openlocfilehash: b944112ce0b00e84da6243e2e48917e2318b0f1c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746843"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="4fb64-102">Метод ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="4fb64-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="4fb64-103">Получает `TypeDef` токен метаданных, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="4fb64-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fb64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fb64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fb64-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="4fb64-106">[out] Указатель на `mdTypeDef` маркер, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="4fb64-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb64-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4fb64-107">Requirements</span></span>  
 <span data-ttu-id="4fb64-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fb64-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb64-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fb64-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fb64-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fb64-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fb64-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb64-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb64-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4fb64-112">See also</span></span>

- [<span data-ttu-id="4fb64-113">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="4fb64-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
