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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 080c16d3a7baceaa277b3418ac2e17391090f00c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750607"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="aeb90-102">Метод ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="aeb90-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="aeb90-103">Создает буфер заданного размера для метода и возвращает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="aeb90-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="aeb90-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="aeb90-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeb90-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aeb90-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aeb90-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="aeb90-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="aeb90-107">[in] Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="aeb90-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="aeb90-108">[out] Возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="aeb90-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="aeb90-109">[out] Относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="aeb90-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aeb90-110">Требования</span><span class="sxs-lookup"><span data-stu-id="aeb90-110">Requirements</span></span>  
 <span data-ttu-id="aeb90-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeb90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aeb90-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aeb90-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aeb90-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aeb90-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aeb90-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeb90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb90-115">См. также</span><span class="sxs-lookup"><span data-stu-id="aeb90-115">See also</span></span>

- [<span data-ttu-id="aeb90-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="aeb90-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
