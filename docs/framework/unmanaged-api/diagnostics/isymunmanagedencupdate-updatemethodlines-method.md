---
title: Метод ISymUnmanagedENCUpdate::UpdateMethodLines
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 226d9aa75d0a9e4d6cef92e2d2edacb6e98cf34e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473062"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>Метод ISymUnmanagedENCUpdate::UpdateMethodLines
Позволяет обновлять данные строки для метода, который не был повторно скомпилирован, но его строки были перемещены независимо друг от друга. Допускается разницы для каждой инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a>Параметры  
 `mdMethodToken`  
 [in] Метаданные маркер метода.  
  
 `pDeltas`  
 [in] Массив `INT32` значений, указывающее «дельты» для каждой точки последовательности в методе.  
  
 `cDeltas`  
 [in] Объект `ULONG` содержащий размер `pDeltas` параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
