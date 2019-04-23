---
title: Метод ISymUnmanagedReader::GetGlobalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e778a5a7baed52941a7f4b990b34d31f8ca84c24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092647"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a>Метод ISymUnmanagedReader::GetGlobalVariables
Возвращает все глобальные переменные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cVars`  
 [in] Размер буфера, на который указывает `pcVars`.  
  
 `pcVars`  
 [out] Указатель на `ULONG32` , принимает размер буфера, требуемого для содержат переменные.  
  
 `pVars`  
 [out] Буфер, содержащий переменные.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
