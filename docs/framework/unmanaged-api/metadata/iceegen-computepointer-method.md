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
ms.openlocfilehash: 9587bbe8f087fd9a51bba67492af1d5acb53ae4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176101"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="f6539-102">Метод ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="f6539-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="f6539-103">Определяет буфер для указанного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="f6539-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="f6539-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="f6539-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6539-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6539-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6539-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6539-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="f6539-107">(в) Раздел кода, для которого можно вернуть буфер.</span><span class="sxs-lookup"><span data-stu-id="f6539-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="f6539-108">(в) Относительный виртуальный адрес метода, для которого можно получить указатель.</span><span class="sxs-lookup"><span data-stu-id="f6539-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="f6539-109">(ваут) Указатель на возвращенный буфер.</span><span class="sxs-lookup"><span data-stu-id="f6539-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6539-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f6539-110">Requirements</span></span>  
 <span data-ttu-id="f6539-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6539-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6539-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6539-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6539-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6539-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6539-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6539-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6539-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f6539-115">See also</span></span>

- [<span data-ttu-id="f6539-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="f6539-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
