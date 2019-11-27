---
title: Метод ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 9e441d4ff39632d9381e445ee99249d04539ad87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427882"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>Метод ISymUnmanagedWriter::RemapToken
Уведомляет средство записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных. Если средство записи символов сохранило Старый токен в хранилище символов, оно должно либо обновить сохраненный токен новым значением, либо сохранить карту для соответствующего средства чтения символов для сопоставления на этапе чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Параметры  
 `oldToken`  
 окне Токен метаданных, который был повторно сопоставлен.  
  
 `newToken`  
 окне Новый маркер метаданных, в который пересопоставлен `oldToken`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
