---
title: Метод ICeeGen::ComputePointer
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79ef272e0c8afa0cd1942416c3a5eb9b825c2e6f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145149"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="7fc03-102">Метод ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="7fc03-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="7fc03-103">Определяет буфер для заданного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="7fc03-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="7fc03-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="7fc03-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc03-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fc03-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fc03-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7fc03-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7fc03-107">[in] В разделе кода, для которого необходимо вернуть в буфер.</span><span class="sxs-lookup"><span data-stu-id="7fc03-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="7fc03-108">[in] Относительный виртуальный адрес метода, для которого необходимо получить указатель.</span><span class="sxs-lookup"><span data-stu-id="7fc03-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="7fc03-109">[out] Указатель на возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="7fc03-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc03-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7fc03-110">Requirements</span></span>  
 <span data-ttu-id="7fc03-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc03-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc03-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7fc03-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fc03-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fc03-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7fc03-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7fc03-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7fc03-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7fc03-115">See also</span></span>

- [<span data-ttu-id="7fc03-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="7fc03-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
