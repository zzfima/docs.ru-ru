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
ms.openlocfilehash: 9e90772ae8c3e6be5744fcccc9901123df871831
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131946"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="cabda-102">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="cabda-102">CoInitializeEE Function</span></span>
<span data-ttu-id="cabda-103">Гарантирует, что подсистема выполнения среды CLR загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="cabda-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="cabda-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cabda-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="cabda-105">Используйте вместо этого метод [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cabda-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cabda-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cabda-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cabda-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="cabda-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="cabda-108">окне Одна из констант перечисления [коинитии](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="cabda-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cabda-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cabda-109">Return Value</span></span>  
 <span data-ttu-id="cabda-110">Этот метод возвращает стандартные коды ошибок COM, определенные в файле Winerror. h, и значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cabda-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="cabda-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="cabda-111">Return code</span></span>|<span data-ttu-id="cabda-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cabda-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cabda-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cabda-113">S_OK</span></span>|<span data-ttu-id="cabda-114">Подсистема выполнения успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="cabda-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="cabda-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cabda-115">S_FALSE</span></span>|<span data-ttu-id="cabda-116">Подсистема выполнения уже загружена.</span><span class="sxs-lookup"><span data-stu-id="cabda-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="cabda-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cabda-117">E_FAIL</span></span>|<span data-ttu-id="cabda-118">Не удалось загрузить подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="cabda-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cabda-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="cabda-119">Remarks</span></span>  
 <span data-ttu-id="cabda-120">Этот метод загружает подсистему выполнения, если он не был загружен ранее.</span><span class="sxs-lookup"><span data-stu-id="cabda-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cabda-121">Требования</span><span class="sxs-lookup"><span data-stu-id="cabda-121">Requirements</span></span>  
 <span data-ttu-id="cabda-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cabda-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cabda-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cabda-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cabda-124">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cabda-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cabda-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cabda-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cabda-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cabda-126">See also</span></span>

- [<span data-ttu-id="cabda-127">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="cabda-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
