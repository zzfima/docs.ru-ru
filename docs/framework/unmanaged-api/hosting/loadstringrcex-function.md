---
title: Функция LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177981"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="2eaab-102">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="2eaab-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="2eaab-103">Переводит значение HRESULT в соответствующее сообщение об ошибке для указанной культуры.</span><span class="sxs-lookup"><span data-stu-id="2eaab-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="2eaab-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="2eaab-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eaab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2eaab-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2eaab-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2eaab-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2eaab-107">(в) Идентификатор культуры.</span><span class="sxs-lookup"><span data-stu-id="2eaab-107">[in] A culture identifier.</span></span> <span data-ttu-id="2eaab-108">Pass -1 `lcid` для использования культуры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eaab-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="2eaab-109">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2eaab-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="2eaab-110">(ваут) Буфер, содержащий сообщение об ошибке при успешном завершении.</span><span class="sxs-lookup"><span data-stu-id="2eaab-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="2eaab-111">(в) Размер буфера сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2eaab-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="2eaab-112">(в) Игнорировать.</span><span class="sxs-lookup"><span data-stu-id="2eaab-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="2eaab-113">(ваут) Указатель на длину сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2eaab-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2eaab-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2eaab-114">Return Value</span></span>  
 <span data-ttu-id="2eaab-115">Этот метод возвращает стандартные коды ошибок COM, как это определено в WinError.h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="2eaab-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="2eaab-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="2eaab-116">Return code</span></span>|<span data-ttu-id="2eaab-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2eaab-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2eaab-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2eaab-118">S_OK</span></span>|<span data-ttu-id="2eaab-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="2eaab-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="2eaab-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2eaab-120">E_INVALIDARG</span></span>|<span data-ttu-id="2eaab-121">`szBuffer`является нулевым, или `iMax` равна нулю (0).</span><span class="sxs-lookup"><span data-stu-id="2eaab-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eaab-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="2eaab-122">Remarks</span></span>  
 <span data-ttu-id="2eaab-123">Если метод не выполняется `szBuffer` успешно, содержитпустую строку.</span><span class="sxs-lookup"><span data-stu-id="2eaab-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eaab-124">Требования</span><span class="sxs-lookup"><span data-stu-id="2eaab-124">Requirements</span></span>  
 <span data-ttu-id="2eaab-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eaab-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eaab-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2eaab-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2eaab-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2eaab-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2eaab-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eaab-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eaab-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2eaab-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2eaab-130">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="2eaab-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="2eaab-131">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="2eaab-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
