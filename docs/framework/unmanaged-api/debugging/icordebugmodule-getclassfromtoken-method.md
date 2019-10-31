---
title: Метод ICorDebugModule::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: 790999093f874a4d81dd5db74ef012b1d997a12f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109649"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="a1ecb-102">Метод ICorDebugModule::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="a1ecb-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="a1ecb-103">Возвращает класс, указанный токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="a1ecb-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ecb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1ecb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1ecb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1ecb-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="a1ecb-106">окне Токен метаданных `mdTypeDef`, ссылающийся на метаданные класса.</span><span class="sxs-lookup"><span data-stu-id="a1ecb-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="a1ecb-107">заполняет Указатель на адрес объекта ICorDebugClass, который представляет класс.</span><span class="sxs-lookup"><span data-stu-id="a1ecb-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1ecb-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a1ecb-108">Requirements</span></span>  
 <span data-ttu-id="a1ecb-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ecb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ecb-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1ecb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1ecb-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1ecb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1ecb-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ecb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
