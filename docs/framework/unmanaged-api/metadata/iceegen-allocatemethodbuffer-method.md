---
title: Метод ICeeGen::AllocateMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 38b9ea2ffab439f55f0a6d34d7f42c7669629168
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177911"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="b14f6-102">Метод ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="b14f6-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="b14f6-103">Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="b14f6-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="b14f6-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="b14f6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b14f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b14f6-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b14f6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b14f6-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="b14f6-107">(в) Длина буфера для создания.</span><span class="sxs-lookup"><span data-stu-id="b14f6-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="b14f6-108">(ваут) Вернулся буфер.</span><span class="sxs-lookup"><span data-stu-id="b14f6-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="b14f6-109">(ваут) Относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="b14f6-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b14f6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b14f6-110">Requirements</span></span>  
 <span data-ttu-id="b14f6-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b14f6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b14f6-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b14f6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b14f6-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b14f6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b14f6-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b14f6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14f6-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b14f6-115">See also</span></span>

- [<span data-ttu-id="b14f6-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b14f6-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
