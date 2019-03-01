---
title: Функция CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca85a12191db51818da2a08910dc9524d1ac9498
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211823"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="93c3e-102">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="93c3e-102">CoInitializeEE Function</span></span>
<span data-ttu-id="93c3e-103">Гарантирует, что ядро выполнения среды выполнения загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="93c3e-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="93c3e-104">Эта функция является устаревшей в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93c3e-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="93c3e-105">Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="93c3e-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c3e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93c3e-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93c3e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="93c3e-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="93c3e-108">[in] Один из [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="93c3e-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93c3e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="93c3e-109">Return Value</span></span>  
 <span data-ttu-id="93c3e-110">Этот метод возвращает стандартные коды ошибок COM, как определено в файле Winerror.h, а также значения в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="93c3e-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="93c3e-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="93c3e-111">Return code</span></span>|<span data-ttu-id="93c3e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="93c3e-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="93c3e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="93c3e-113">S_OK</span></span>|<span data-ttu-id="93c3e-114">Подсистема выполнения была успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="93c3e-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="93c3e-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="93c3e-115">S_FALSE</span></span>|<span data-ttu-id="93c3e-116">Подсистема выполнения уже загружен.</span><span class="sxs-lookup"><span data-stu-id="93c3e-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="93c3e-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93c3e-117">E_FAIL</span></span>|<span data-ttu-id="93c3e-118">Не удалось загрузить подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="93c3e-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93c3e-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="93c3e-119">Remarks</span></span>  
 <span data-ttu-id="93c3e-120">Этот метод загружает ядро выполнения, если он не был загружен ранее.</span><span class="sxs-lookup"><span data-stu-id="93c3e-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93c3e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="93c3e-121">Requirements</span></span>  
 <span data-ttu-id="93c3e-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93c3e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93c3e-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="93c3e-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93c3e-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93c3e-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93c3e-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93c3e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c3e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="93c3e-126">See also</span></span>
- [<span data-ttu-id="93c3e-127">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="93c3e-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
