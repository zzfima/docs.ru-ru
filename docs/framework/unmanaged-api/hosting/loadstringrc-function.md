---
title: Функция LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 66d4c14234c7929af443922f86098b46a4aa6eb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122017"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="60dc3-102">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="60dc3-102">LoadStringRC Function</span></span>
<span data-ttu-id="60dc3-103">Преобразует значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.</span><span class="sxs-lookup"><span data-stu-id="60dc3-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="60dc3-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="60dc3-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60dc3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60dc3-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60dc3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="60dc3-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="60dc3-107">окне Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="60dc3-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="60dc3-108">заполняет Буфер, содержащий сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="60dc3-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="60dc3-109">окне Размер буфера сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="60dc3-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="60dc3-110">окне Игнорируют.</span><span class="sxs-lookup"><span data-stu-id="60dc3-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60dc3-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="60dc3-111">Return Value</span></span>  
 <span data-ttu-id="60dc3-112">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="60dc3-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="60dc3-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="60dc3-113">Return code</span></span>|<span data-ttu-id="60dc3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="60dc3-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="60dc3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="60dc3-115">S_OK</span></span>|<span data-ttu-id="60dc3-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="60dc3-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="60dc3-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="60dc3-117">E_INVALIDARG</span></span>|<span data-ttu-id="60dc3-118">`szBuffer` имеет значение null или `iMax` равен нулю (0).</span><span class="sxs-lookup"><span data-stu-id="60dc3-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60dc3-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="60dc3-119">Remarks</span></span>  
 <span data-ttu-id="60dc3-120">Если метод не завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="60dc3-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60dc3-121">Требования</span><span class="sxs-lookup"><span data-stu-id="60dc3-121">Requirements</span></span>  
 <span data-ttu-id="60dc3-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60dc3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60dc3-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60dc3-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60dc3-124">**Библиотека:** MSCorEE. dll и mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="60dc3-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="60dc3-125">Используйте библиотеку MSCorEE. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60dc3-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="60dc3-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60dc3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60dc3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="60dc3-127">See also</span></span>

- [<span data-ttu-id="60dc3-128">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="60dc3-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="60dc3-129">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="60dc3-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
