---
title: Метод IMetaDataError::OnError
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: 489fa217744e41ccb5d27d088790131c15e1ee52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177401"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="4c6a6-102">Метод IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="4c6a6-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="4c6a6-103">Предоставляет уведомление об ошибках, возникающих при слиянии метаданных.</span><span class="sxs-lookup"><span data-stu-id="4c6a6-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c6a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c6a6-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c6a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c6a6-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="4c6a6-106">(в) Значение ошибки HRESULT возвращается к методу вызова.</span><span class="sxs-lookup"><span data-stu-id="4c6a6-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="4c6a6-107">(в) Токен метаданных объекта кода, который был объединен при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="4c6a6-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c6a6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4c6a6-108">Requirements</span></span>  
 <span data-ttu-id="4c6a6-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c6a6-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4c6a6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c6a6-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c6a6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c6a6-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c6a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6a6-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c6a6-113">See also</span></span>

- [<span data-ttu-id="4c6a6-114">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="4c6a6-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
