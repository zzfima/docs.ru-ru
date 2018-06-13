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
ms.openlocfilehash: 1dccb2a3a3f3aaf0f209c8f3543056ab81c562dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443903"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="269d1-102">Метод ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="269d1-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="269d1-103">Выдает заданную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="269d1-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="269d1-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="269d1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269d1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="269d1-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="269d1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="269d1-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="269d1-107">[in] Строка для выпуска.</span><span class="sxs-lookup"><span data-stu-id="269d1-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="269d1-108">[out] Относительный виртуальный адрес порожденную строки.</span><span class="sxs-lookup"><span data-stu-id="269d1-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="269d1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="269d1-109">Requirements</span></span>  
 <span data-ttu-id="269d1-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="269d1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="269d1-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="269d1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="269d1-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="269d1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="269d1-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="269d1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269d1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="269d1-114">See Also</span></span>  
 [<span data-ttu-id="269d1-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="269d1-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
