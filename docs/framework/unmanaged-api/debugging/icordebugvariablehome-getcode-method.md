---
title: 'Метод ICorDebugVariableHome:: с кодом'
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
ms.openlocfilehash: fdfa38a4cdbbaad2fc2c987a10a122af4a1fc9a9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791040"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="3f334-102">Метод ICorDebugVariableHome:: с кодом</span><span class="sxs-lookup"><span data-stu-id="3f334-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="3f334-103">Возвращает экземпляр "ICorDebugCode", который содержит этот объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3f334-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f334-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f334-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f334-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f334-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="3f334-106">заполняет Указатель на адрес экземпляра ICorDebugCode, который содержит этот объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3f334-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f334-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3f334-107">Requirements</span></span>  
 <span data-ttu-id="3f334-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f334-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f334-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f334-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f334-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f334-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f334-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f334-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f334-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f334-112">See also</span></span>

- [<span data-ttu-id="3f334-113">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="3f334-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
