---
title: Метод ICeeGen::EmitString
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1eabf5631fcfe7a187d0e203d64c7a7f4f5a819a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209961"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="cca71-102">Метод ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="cca71-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="cca71-103">Создает указанную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="cca71-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="cca71-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="cca71-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca71-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cca71-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cca71-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cca71-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="cca71-107">[in] Строка для выпуска.</span><span class="sxs-lookup"><span data-stu-id="cca71-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="cca71-108">[out] Относительный виртуальный адрес порожденную строки.</span><span class="sxs-lookup"><span data-stu-id="cca71-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cca71-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cca71-109">Requirements</span></span>  
 <span data-ttu-id="cca71-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cca71-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cca71-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cca71-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cca71-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cca71-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cca71-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cca71-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cca71-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cca71-114">See also</span></span>

- [<span data-ttu-id="cca71-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="cca71-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
