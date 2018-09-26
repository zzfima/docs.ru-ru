---
title: Метод IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a0b3242e8ae29b9d21dc50d3ea0476967e9746f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47192866"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="f2b94-102">Метод IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="f2b94-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="f2b94-103">Создает поток с указанным именем и формат.</span><span class="sxs-lookup"><span data-stu-id="f2b94-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2b94-104">Syntax</span></span>  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2b94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2b94-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="f2b94-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="f2b94-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="f2b94-107">[in] Имя потока, который должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="f2b94-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="f2b94-108">[in] Формат файла для потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="f2b94-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="f2b94-109">[in] Флаги определенного формата, определенного в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="f2b94-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="f2b94-110">[out] Указатель на адрес возвращаемого [IStream](/windows/desktop/api/objidl/nn-objidl-istream) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f2b94-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="f2b94-111">[in, optional] Максимальный размер потока, который ссылается `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="f2b94-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2b94-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f2b94-112">Requirements</span></span>  
 <span data-ttu-id="f2b94-113">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2b94-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b94-114">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f2b94-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f2b94-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2b94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b94-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f2b94-116">See Also</span></span>  
 [<span data-ttu-id="f2b94-117">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="f2b94-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
