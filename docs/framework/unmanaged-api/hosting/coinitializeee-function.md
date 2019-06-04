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
ms.openlocfilehash: 9597b12b0da6df807b2d4eaa42c2035c518b71d9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490627"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="83a5d-102">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="83a5d-102">CoInitializeEE Function</span></span>
<span data-ttu-id="83a5d-103">Гарантирует, что ядро выполнения среды выполнения загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="83a5d-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="83a5d-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="83a5d-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="83a5d-105">Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="83a5d-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a5d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83a5d-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83a5d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="83a5d-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="83a5d-108">[in] Один из [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="83a5d-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83a5d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83a5d-109">Return Value</span></span>  
 <span data-ttu-id="83a5d-110">Этот метод возвращает стандартные коды ошибок COM, как определено в файле Winerror.h, а также значения в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="83a5d-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="83a5d-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="83a5d-111">Return code</span></span>|<span data-ttu-id="83a5d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="83a5d-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="83a5d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="83a5d-113">S_OK</span></span>|<span data-ttu-id="83a5d-114">Подсистема выполнения была успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="83a5d-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="83a5d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="83a5d-115">S_FALSE</span></span>|<span data-ttu-id="83a5d-116">Подсистема выполнения уже загружен.</span><span class="sxs-lookup"><span data-stu-id="83a5d-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="83a5d-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83a5d-117">E_FAIL</span></span>|<span data-ttu-id="83a5d-118">Не удалось загрузить подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="83a5d-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83a5d-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="83a5d-119">Remarks</span></span>  
 <span data-ttu-id="83a5d-120">Этот метод загружает ядро выполнения, если он не был загружен ранее.</span><span class="sxs-lookup"><span data-stu-id="83a5d-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a5d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="83a5d-121">Requirements</span></span>  
 <span data-ttu-id="83a5d-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83a5d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83a5d-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="83a5d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83a5d-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83a5d-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83a5d-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83a5d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a5d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="83a5d-126">See also</span></span>

- [<span data-ttu-id="83a5d-127">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="83a5d-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
