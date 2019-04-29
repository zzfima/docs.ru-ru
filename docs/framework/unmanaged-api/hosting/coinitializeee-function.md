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
ms.openlocfilehash: 18f1a4ede1a362860df1271835600e7b867eac00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696929"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="c92dc-102">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="c92dc-102">CoInitializeEE Function</span></span>
<span data-ttu-id="c92dc-103">Гарантирует, что ядро выполнения среды выполнения загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="c92dc-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="c92dc-104">Эта функция является устаревшей в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c92dc-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c92dc-105">Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c92dc-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c92dc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c92dc-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c92dc-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c92dc-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="c92dc-108">[in] Один из [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="c92dc-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c92dc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c92dc-109">Return Value</span></span>  
 <span data-ttu-id="c92dc-110">Этот метод возвращает стандартные коды ошибок COM, как определено в файле Winerror.h, а также значения в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c92dc-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="c92dc-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="c92dc-111">Return code</span></span>|<span data-ttu-id="c92dc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c92dc-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c92dc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c92dc-113">S_OK</span></span>|<span data-ttu-id="c92dc-114">Подсистема выполнения была успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="c92dc-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="c92dc-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c92dc-115">S_FALSE</span></span>|<span data-ttu-id="c92dc-116">Подсистема выполнения уже загружен.</span><span class="sxs-lookup"><span data-stu-id="c92dc-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="c92dc-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c92dc-117">E_FAIL</span></span>|<span data-ttu-id="c92dc-118">Не удалось загрузить подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="c92dc-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c92dc-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c92dc-119">Remarks</span></span>  
 <span data-ttu-id="c92dc-120">Этот метод загружает ядро выполнения, если он не был загружен ранее.</span><span class="sxs-lookup"><span data-stu-id="c92dc-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c92dc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c92dc-121">Requirements</span></span>  
 <span data-ttu-id="c92dc-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c92dc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c92dc-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c92dc-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c92dc-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c92dc-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c92dc-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c92dc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92dc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c92dc-126">See also</span></span>

- [<span data-ttu-id="c92dc-127">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="c92dc-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
