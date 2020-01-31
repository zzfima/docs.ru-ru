---
title: Метод ICorPublishProcess::GetProcessID
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790559"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="6c4aa-102">Метод ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="6c4aa-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="6c4aa-103">Возвращает идентификатор операционной системы для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="6c4aa-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c4aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c4aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c4aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c4aa-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="6c4aa-106">заполняет Указатель на идентификатор процесса, представленного этим объектом [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6c4aa-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c4aa-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6c4aa-107">Requirements</span></span>  
 <span data-ttu-id="6c4aa-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c4aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c4aa-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="6c4aa-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6c4aa-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c4aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c4aa-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c4aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c4aa-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c4aa-112">See also</span></span>

- [<span data-ttu-id="6c4aa-113">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="6c4aa-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
