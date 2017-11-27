---
title: "Функция CreateHistoryReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="fc77d-102">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="fc77d-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="fc77d-103">Создает средство чтения журнала для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="fc77d-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc77d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc77d-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc77d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc77d-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="fc77d-106">[in] Путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="fc77d-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="fc77d-107">[out] При успешном завершении содержит указатель на чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="fc77d-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc77d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc77d-108">Return Value</span></span>  
 <span data-ttu-id="fc77d-109">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, помимо значений, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fc77d-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="fc77d-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="fc77d-110">Return code</span></span>|<span data-ttu-id="fc77d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="fc77d-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fc77d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc77d-112">S_OK</span></span>|<span data-ttu-id="fc77d-113">Указывает на успешное завершение метода.</span><span class="sxs-lookup"><span data-stu-id="fc77d-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="fc77d-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fc77d-114">E_INVALIDARG</span></span>|<span data-ttu-id="fc77d-115">Указывает, что `wzFilePath` или `ppHistoryReader` присваивается указатель null.</span><span class="sxs-lookup"><span data-stu-id="fc77d-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc77d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="fc77d-116">Requirements</span></span>  
 <span data-ttu-id="fc77d-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc77d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc77d-118">**Библиотека:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="fc77d-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="fc77d-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc77d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc77d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fc77d-120">See Also</span></span>  
 [<span data-ttu-id="fc77d-121">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="fc77d-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
