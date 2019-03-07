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
ms.openlocfilehash: 413e56a65f4966467f487787172973834ac4a65a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496876"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="4767e-102">Метод ICorDebugModule::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="4767e-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="4767e-103">Возвращает класс, указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="4767e-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4767e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4767e-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4767e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4767e-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="4767e-106">[in] `mdTypeDef` Токен метаданных, который ссылается на метаданные класса.</span><span class="sxs-lookup"><span data-stu-id="4767e-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="4767e-107">[out] Указатель на адрес объекта ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="4767e-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4767e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4767e-108">Requirements</span></span>  
 <span data-ttu-id="4767e-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4767e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4767e-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4767e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4767e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4767e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4767e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4767e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
