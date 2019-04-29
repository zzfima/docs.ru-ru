---
title: Метод IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f70187ba9bd71225162e6e10184e4992b5600f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645166"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="2be2a-102">Метод IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="2be2a-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="2be2a-103">Получает имя, размер и содержимое потока метаданных по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="2be2a-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2be2a-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2be2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2be2a-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="2be2a-106">[in] Индекс потока запрошенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="2be2a-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="2be2a-107">[out] Указатель на имя потока.</span><span class="sxs-lookup"><span data-stu-id="2be2a-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2be2a-108">[out] Указатель на поток метаданных.</span><span class="sxs-lookup"><span data-stu-id="2be2a-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="2be2a-109">[out] Размер в байтах из `ppv`.</span><span class="sxs-lookup"><span data-stu-id="2be2a-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be2a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2be2a-110">Requirements</span></span>  
 <span data-ttu-id="2be2a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2be2a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be2a-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2be2a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2be2a-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2be2a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2be2a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2be2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be2a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2be2a-115">See also</span></span>

- [<span data-ttu-id="2be2a-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="2be2a-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="2be2a-117">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="2be2a-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
