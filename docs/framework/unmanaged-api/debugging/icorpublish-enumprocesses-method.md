---
title: Метод ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121795"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="41cb8-102">Метод ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="41cb8-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="41cb8-103">Возвращает перечислитель для управляемых процессов, выполняющихся на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="41cb8-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41cb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41cb8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41cb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41cb8-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="41cb8-106">Значение перечисления [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) , указывающее тип получаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="41cb8-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="41cb8-107">В текущей версии допускается только COR_PUB_MANAGEDONLY.</span><span class="sxs-lookup"><span data-stu-id="41cb8-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="41cb8-108">Указатель на адрес экземпляра [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) , который является перечислителем процессов.</span><span class="sxs-lookup"><span data-stu-id="41cb8-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41cb8-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="41cb8-109">Remarks</span></span>  
 <span data-ttu-id="41cb8-110">Коллекция процессов перечислителя основана на моментальном снимке процессов, выполняемых при вызове метода `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="41cb8-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="41cb8-111">Перечислитель не будет включать процессы, которые завершаются до или после вызова `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="41cb8-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="41cb8-112">Метод `EnumProcesses` может быть вызван более одного раза в этом экземпляре [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) для создания новой актуальной коллекции процессов.</span><span class="sxs-lookup"><span data-stu-id="41cb8-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="41cb8-113">Последующие вызовы метода `EnumProcesses` не будут затронуты существующими коллекциями.</span><span class="sxs-lookup"><span data-stu-id="41cb8-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41cb8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="41cb8-114">Requirements</span></span>  
 <span data-ttu-id="41cb8-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41cb8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cb8-116">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="41cb8-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="41cb8-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41cb8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41cb8-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41cb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cb8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="41cb8-119">See also</span></span>

- [<span data-ttu-id="41cb8-120">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="41cb8-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
