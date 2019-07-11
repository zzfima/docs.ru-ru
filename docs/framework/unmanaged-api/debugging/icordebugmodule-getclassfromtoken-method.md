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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6da6fabc6632bea58b28a00f55d05f4c2cc5b46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762677"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="1c07f-102">Метод ICorDebugModule::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="1c07f-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="1c07f-103">Возвращает класс, указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="1c07f-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c07f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c07f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c07f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c07f-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="1c07f-106">[in] `mdTypeDef` Токен метаданных, который ссылается на метаданные класса.</span><span class="sxs-lookup"><span data-stu-id="1c07f-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="1c07f-107">[out] Указатель на адрес объекта ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="1c07f-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c07f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1c07f-108">Requirements</span></span>  
 <span data-ttu-id="1c07f-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c07f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c07f-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c07f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c07f-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c07f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c07f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c07f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
