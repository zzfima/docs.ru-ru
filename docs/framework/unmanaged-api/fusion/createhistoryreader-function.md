---
title: Функция CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3a3cc21dbbcfa99ddcecb534bd2e337da005597
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="ed22c-102">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="ed22c-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="ed22c-103">Создает средство чтения журнала для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="ed22c-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed22c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed22c-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed22c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed22c-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="ed22c-106">[in] Путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="ed22c-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="ed22c-107">[out] При успешном завершении содержит указатель на чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="ed22c-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed22c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed22c-108">Return Value</span></span>  
 <span data-ttu-id="ed22c-109">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, помимо значений, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ed22c-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="ed22c-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="ed22c-110">Return code</span></span>|<span data-ttu-id="ed22c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ed22c-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ed22c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed22c-112">S_OK</span></span>|<span data-ttu-id="ed22c-113">Указывает на успешное завершение метода.</span><span class="sxs-lookup"><span data-stu-id="ed22c-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="ed22c-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ed22c-114">E_INVALIDARG</span></span>|<span data-ttu-id="ed22c-115">Указывает, что `wzFilePath` или `ppHistoryReader` присваивается указатель null.</span><span class="sxs-lookup"><span data-stu-id="ed22c-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed22c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ed22c-116">Requirements</span></span>  
 <span data-ttu-id="ed22c-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed22c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed22c-118">**Библиотека:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="ed22c-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="ed22c-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed22c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed22c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ed22c-120">See Also</span></span>  
 [<span data-ttu-id="ed22c-121">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="ed22c-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
