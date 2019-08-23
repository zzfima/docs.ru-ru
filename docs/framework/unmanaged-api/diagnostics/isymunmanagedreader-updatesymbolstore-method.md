---
title: Метод ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d84d4fccb2cb4e500f07f6bfbfb93b8c7b81f5d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939006"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>Метод ISymUnmanagedReader::UpdateSymbolStore
Обновляет существующее хранилище символов разностным хранилищем символов. Этот метод используется в сценариях "изменить и продолжить" для обновления хранилища символов в соответствии с разностью с исходным переносимым исполняемым файлом (PE).  
  
> [!NOTE]
> Необходимо указать только один из `filename` параметров или `pIStream` , но не оба. Если `filename` указан параметр, хранилище символов будет обновлено символами из этого файла. Если `pIStream` указан параметр, хранилище будет обновляться данными <xref:System.Runtime.InteropServices.ComTypes.IStream>из.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Параметры  
 `filename`  
 окне Имя файла, содержащего хранилище символов.  
  
 `pIStream`  
 окне Файловый поток, используемый в качестве альтернативы `filename` параметру.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
