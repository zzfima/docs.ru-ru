---
title: Метод ICLRMetadataLocator::GetMetadata
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e677aefd5420f71867c1f11a2c9408c77d305c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697840"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="13057-102">Метод ICLRMetadataLocator::GetMetadata</span><span class="sxs-lookup"><span data-stu-id="13057-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="13057-103">Вызывается службами доступа к данным среды выполнения (CLR) для получения метаданных изображения.</span><span class="sxs-lookup"><span data-stu-id="13057-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13057-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13057-104">Syntax</span></span>  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13057-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13057-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="13057-106">[in] Строка, указывающая путь к файлу изображения.</span><span class="sxs-lookup"><span data-stu-id="13057-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="13057-107">[in] Метка времени файла изображения.</span><span class="sxs-lookup"><span data-stu-id="13057-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="13057-108">[in] Размер файла изображения.</span><span class="sxs-lookup"><span data-stu-id="13057-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="13057-109">[in] Глобальный уникальный идентификатор изображения.</span><span class="sxs-lookup"><span data-stu-id="13057-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="13057-110">[in] Относительный виртуальный адрес (RVA) метаданных.</span><span class="sxs-lookup"><span data-stu-id="13057-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="13057-111">Адрес задается относительно базового адреса образа.</span><span class="sxs-lookup"><span data-stu-id="13057-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="13057-112">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="13057-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="13057-113">[in] Размер буфера для размещения метаданных.</span><span class="sxs-lookup"><span data-stu-id="13057-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="13057-114">[out] Буфер, в котором следует разместить метаданные.</span><span class="sxs-lookup"><span data-stu-id="13057-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="13057-115">[out] Размер метаданных, который возвращается.</span><span class="sxs-lookup"><span data-stu-id="13057-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13057-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="13057-116">Remarks</span></span>  
 <span data-ttu-id="13057-117">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="13057-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13057-118">Требования</span><span class="sxs-lookup"><span data-stu-id="13057-118">Requirements</span></span>  
 <span data-ttu-id="13057-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13057-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13057-120">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="13057-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="13057-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13057-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13057-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13057-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13057-123">См. также</span><span class="sxs-lookup"><span data-stu-id="13057-123">See also</span></span>

- [<span data-ttu-id="13057-124">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="13057-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
