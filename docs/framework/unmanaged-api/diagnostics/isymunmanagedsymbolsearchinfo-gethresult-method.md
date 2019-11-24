---
title: Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: 21f6cf18ee7d883e1792b597e08724946f53eda9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446187"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a>Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT
Gets the HRESULT.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a>Параметры  
 `phr`  
 [out] A pointer to the HRESULT.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK if the method succeeds; otherwise, E_FAIL or some other error code.  
  
## <a name="requirements"></a>Требования  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
