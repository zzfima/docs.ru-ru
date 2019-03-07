---
title: Метод ICeeGen::GetString
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf3f781e23d0787d01a1ef04b41b2c38eaaa9e0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479341"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="1dd1b-102">Метод ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="1dd1b-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="1dd1b-103">Получает строку, хранящуюся в указанный относительный виртуальный адрес.</span><span class="sxs-lookup"><span data-stu-id="1dd1b-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="1dd1b-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="1dd1b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dd1b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1dd1b-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dd1b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1dd1b-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="1dd1b-107">[in] Относительный виртуальный адрес возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="1dd1b-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="1dd1b-108">[out] Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="1dd1b-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dd1b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1dd1b-109">Requirements</span></span>  
 <span data-ttu-id="1dd1b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dd1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dd1b-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1dd1b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1dd1b-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1dd1b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1dd1b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dd1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd1b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1dd1b-114">See also</span></span>
- [<span data-ttu-id="1dd1b-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="1dd1b-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
