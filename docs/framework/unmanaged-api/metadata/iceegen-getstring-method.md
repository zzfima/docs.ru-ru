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
ms.openlocfilehash: f7ac5ef95ca3705b11cfda51d7fd1aca7400abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443077"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="06ba3-102">Метод ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="06ba3-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="06ba3-103">Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="06ba3-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="06ba3-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="06ba3-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ba3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06ba3-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06ba3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="06ba3-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="06ba3-107">[in] Относительный виртуальный адрес возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="06ba3-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="06ba3-108">[out] Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="06ba3-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ba3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="06ba3-109">Requirements</span></span>  
 <span data-ttu-id="06ba3-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ba3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ba3-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="06ba3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06ba3-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06ba3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06ba3-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ba3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ba3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="06ba3-114">See Also</span></span>  
 [<span data-ttu-id="06ba3-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="06ba3-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
