---
title: "Метод IAssemblyCacheItem::CreateStream"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.CreateStream
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8dfdb34e10c6bc47ce13230ee03ef024cb15b07b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="dc586-102">Метод IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="dc586-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="dc586-103">Создает поток с указанным именем и формат.</span><span class="sxs-lookup"><span data-stu-id="dc586-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc586-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc586-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="dc586-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc586-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="dc586-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="dc586-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="dc586-107">[in] Имя потока, который должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="dc586-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="dc586-108">[in] Формат файла для потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="dc586-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="dc586-109">[in] Флаги определенного формата, определенных в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="dc586-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="dc586-110">[out] Указатель на адрес возвращаемого <xref:IStream> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dc586-110">[out] A pointer to the address of the returned <xref:IStream> instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="dc586-111">[in, необязательно] Максимальный размер потока ссылается `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="dc586-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc586-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dc586-112">Requirements</span></span>  
 <span data-ttu-id="dc586-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc586-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc586-114">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="dc586-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dc586-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc586-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc586-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dc586-116">See Also</span></span>  
 [<span data-ttu-id="dc586-117">IAssemblyCacheItem-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dc586-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
