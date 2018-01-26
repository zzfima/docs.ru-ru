---
title: "Метод ICLRMetadataLocator::GetMetadata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetadataLocator.GetMetadata
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8758a96464d1465d92fb17314f1e36ab8d9169c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>Метод ICLRMetadataLocator::GetMetadata
Вызывается службами доступа к данным среды выполнения (CLR) для получения метаданных изображения.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `imagePath`  
 [in] Строка, указывающая путь к файлу изображения.  
  
 `imageTimestamp`  
 [in] Отметка времени файла изображения.  
  
 `imageSize`  
 [in] Размер файла изображения.  
  
 `mvid`  
 [in] Глобальный уникальный идентификатор изображения.  
  
 `mdRva`  
 [in] Относительный виртуальный адрес (RVA) метаданных. Адрес задается относительно базового адреса образа.  
  
 `flags`  
 [in] Зарезервировано для будущего использования.  
  
 `bufferSize`  
 [in] Размер буфера, в который следует поместить в метаданные.  
  
 `buffer`  
 [out] Буфер, в который следует поместить в метаданные.  
  
 `dataSize`  
 [out] Размер метаданных, которое возвращается.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRMetadataLocator](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
