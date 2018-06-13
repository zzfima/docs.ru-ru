---
title: Метод ICorDebugVariableHome::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee8fa8feebba7258fc84ee7ba00ce2ab1977faa4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420408"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="9ddbf-102">Метод ICorDebugVariableHome::GetCode</span><span class="sxs-lookup"><span data-stu-id="9ddbf-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="9ddbf-103">Возвращает экземпляр «ICorDebugCode», содержащий это [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="9ddbf-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ddbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ddbf-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ddbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ddbf-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="9ddbf-106">[out] Указатель на адрес экземпляра «ICorDebugCode», содержащий это [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="9ddbf-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ddbf-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9ddbf-107">Requirements</span></span>  
 <span data-ttu-id="9ddbf-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ddbf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddbf-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ddbf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ddbf-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ddbf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ddbf-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddbf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddbf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9ddbf-112">See Also</span></span>  
 [<span data-ttu-id="9ddbf-113">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="9ddbf-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 
