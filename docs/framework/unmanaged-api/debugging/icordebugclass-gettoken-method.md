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
ms.openlocfilehash: f67bd427c83385b2433b9f2e97f0b54e3b29a76f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401067"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="fbc64-102">Метод ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="fbc64-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="fbc64-103">Возвращает `TypeDef` токен метаданных, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="fbc64-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbc64-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fbc64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbc64-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="fbc64-106">[out] Указатель на `mdTypeDef` маркер, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="fbc64-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbc64-107">Требования</span><span class="sxs-lookup"><span data-stu-id="fbc64-107">Requirements</span></span>  
 <span data-ttu-id="fbc64-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbc64-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbc64-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbc64-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbc64-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbc64-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbc64-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbc64-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc64-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fbc64-112">See Also</span></span>  
 [<span data-ttu-id="fbc64-113">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="fbc64-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
