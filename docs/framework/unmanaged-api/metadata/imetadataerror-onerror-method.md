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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ed9e097dccd0fcb81ea9023cc9b84906589ccb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446262"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="f041e-102">Метод IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="f041e-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="f041e-103">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="f041e-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f041e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f041e-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f041e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f041e-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="f041e-106">[in] Значение HRESULT ошибки, возвращаемый вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="f041e-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="f041e-107">[in] Токен метаданных объекта кода объединенные возникшей ошибки.</span><span class="sxs-lookup"><span data-stu-id="f041e-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f041e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f041e-108">Requirements</span></span>  
 <span data-ttu-id="f041e-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f041e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f041e-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f041e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f041e-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f041e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f041e-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f041e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f041e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f041e-113">See Also</span></span>  
 [<span data-ttu-id="f041e-114">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="f041e-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
