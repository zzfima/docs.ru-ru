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
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176244"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="306cc-102">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="306cc-102">LoadStringRC Function</span></span>
<span data-ttu-id="306cc-103">Преобразует значение HRESULT в сообщение об ошибке, используя культуру по умолчанию текущего потока.</span><span class="sxs-lookup"><span data-stu-id="306cc-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="306cc-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="306cc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="306cc-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="306cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="306cc-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="306cc-107">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="306cc-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="306cc-108">(ваут) Буфер, содержащий сообщение об ошибке при успешном завершении.</span><span class="sxs-lookup"><span data-stu-id="306cc-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="306cc-109">(в) Размер буфера сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="306cc-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="306cc-110">(в) Игнорировать.</span><span class="sxs-lookup"><span data-stu-id="306cc-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="306cc-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="306cc-111">Return Value</span></span>  
 <span data-ttu-id="306cc-112">Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="306cc-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="306cc-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="306cc-113">Return code</span></span>|<span data-ttu-id="306cc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="306cc-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="306cc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="306cc-115">S_OK</span></span>|<span data-ttu-id="306cc-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="306cc-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="306cc-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="306cc-117">E_INVALIDARG</span></span>|<span data-ttu-id="306cc-118">`szBuffer`является нулевым или `iMax` нулевым (0).</span><span class="sxs-lookup"><span data-stu-id="306cc-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="306cc-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="306cc-119">Remarks</span></span>  
 <span data-ttu-id="306cc-120">Если метод не выполняется `szBuffer` успешно, содержитпустую строку.</span><span class="sxs-lookup"><span data-stu-id="306cc-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306cc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="306cc-121">Requirements</span></span>  
 <span data-ttu-id="306cc-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306cc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306cc-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="306cc-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="306cc-124">**Библиотека:** MSCorEE.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="306cc-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="306cc-125">Используйте MSCorEE.dll вместо Mscorwks.dll, чтобы убедиться, что вы ориентируетесь на правильную версию рамочной программы .NET.</span><span class="sxs-lookup"><span data-stu-id="306cc-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="306cc-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306cc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306cc-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="306cc-127">See also</span></span>

- [<span data-ttu-id="306cc-128">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="306cc-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="306cc-129">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="306cc-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
