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
ms.openlocfilehash: 8057406552525be19f8e6457de9faf841edc6e68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429505"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="83b15-102">Метод IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="83b15-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="83b15-103">Создает поток с указанным именем и формат.</span><span class="sxs-lookup"><span data-stu-id="83b15-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83b15-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="83b15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83b15-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="83b15-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="83b15-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="83b15-107">[in] Имя потока, который должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="83b15-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="83b15-108">[in] Формат файла для потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="83b15-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="83b15-109">[in] Флаги определенного формата, определенных в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="83b15-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="83b15-110">[out] Указатель на адрес возвращаемого [IStream](https://msdn.microsoft.com/library/aa380034.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="83b15-110">[out] A pointer to the address of the returned [IStream](https://msdn.microsoft.com/library/aa380034.aspx) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="83b15-111">[in, необязательно] Максимальный размер потока ссылается `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="83b15-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b15-112">Требования</span><span class="sxs-lookup"><span data-stu-id="83b15-112">Requirements</span></span>  
 <span data-ttu-id="83b15-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83b15-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b15-114">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="83b15-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="83b15-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b15-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b15-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83b15-116">See Also</span></span>  
 [<span data-ttu-id="83b15-117">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="83b15-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
