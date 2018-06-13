---
title: Метод ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0412089fee27e556c2f9230e9b34de3391b9bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402565"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="b42b5-102">Метод ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="b42b5-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="b42b5-103">Возвращает значение, показывающее, присоединен ли отладчик в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="b42b5-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b42b5-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b42b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b42b5-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="b42b5-106">[out] `true` Если отладчик присоединен к домену приложения; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="b42b5-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b42b5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b42b5-107">Remarks</span></span>  
 <span data-ttu-id="b42b5-108">Методы ICorDebugController нельзя, пока отладчик подключается к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="b42b5-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b42b5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b42b5-109">Requirements</span></span>  
 <span data-ttu-id="b42b5-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b42b5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b42b5-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b42b5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b42b5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b42b5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b42b5-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b42b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
