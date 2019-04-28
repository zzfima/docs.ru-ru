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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750769"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="9cde3-102">Метод ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="9cde3-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="9cde3-103">Получает `TypeDef` токен метаданных, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="9cde3-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cde3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cde3-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cde3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cde3-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="9cde3-106">[out] Указатель на `mdTypeDef` маркер, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="9cde3-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cde3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9cde3-107">Requirements</span></span>  
 <span data-ttu-id="9cde3-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cde3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cde3-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cde3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cde3-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cde3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cde3-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cde3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cde3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9cde3-112">See also</span></span>

- [<span data-ttu-id="9cde3-113">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="9cde3-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
