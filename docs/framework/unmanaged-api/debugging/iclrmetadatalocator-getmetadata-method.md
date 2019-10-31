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
ms.openlocfilehash: 1f28a4b4acd9d6050d33b9824aa49a9b9041b59b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111250"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="01734-102">Метод ICLRMetadataLocator::GetMetadata</span><span class="sxs-lookup"><span data-stu-id="01734-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="01734-103">Вызывается службами доступа к данным среды CLR для получения метаданных изображения.</span><span class="sxs-lookup"><span data-stu-id="01734-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01734-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01734-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="01734-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01734-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="01734-106">окне Строка, указывающая путь к файлу изображения.</span><span class="sxs-lookup"><span data-stu-id="01734-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="01734-107">окне Метка времени файла изображения.</span><span class="sxs-lookup"><span data-stu-id="01734-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="01734-108">окне Размер файла изображения.</span><span class="sxs-lookup"><span data-stu-id="01734-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="01734-109">окне Глобальный уникальный идентификатор изображения.</span><span class="sxs-lookup"><span data-stu-id="01734-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="01734-110">окне Относительный виртуальный адрес (RVA) метаданных.</span><span class="sxs-lookup"><span data-stu-id="01734-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="01734-111">Адрес отсчитывается относительно базового адреса образа.</span><span class="sxs-lookup"><span data-stu-id="01734-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="01734-112">окне Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="01734-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="01734-113">окне Размер буфера, в который следует поместить метаданные.</span><span class="sxs-lookup"><span data-stu-id="01734-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="01734-114">заполняет Буфер для размещения метаданных.</span><span class="sxs-lookup"><span data-stu-id="01734-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="01734-115">заполняет Размер возвращаемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="01734-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01734-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="01734-116">Remarks</span></span>  
 <span data-ttu-id="01734-117">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="01734-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01734-118">Требования</span><span class="sxs-lookup"><span data-stu-id="01734-118">Requirements</span></span>  
 <span data-ttu-id="01734-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01734-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01734-120">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="01734-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="01734-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01734-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01734-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01734-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01734-123">См. также</span><span class="sxs-lookup"><span data-stu-id="01734-123">See also</span></span>

- [<span data-ttu-id="01734-124">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="01734-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
