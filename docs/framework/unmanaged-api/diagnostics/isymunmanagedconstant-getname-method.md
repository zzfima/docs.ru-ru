---
title: Метод ISymUnmanagedConstant::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 924feaeb91b42404461ad5d276c0cb77279d4dc4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449278"
---
# <a name="isymunmanagedconstantgetname-method"></a>Метод ISymUnmanagedConstant::GetName
Gets the name of the constant.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cchName`  
 [in] The length of the buffer that the `szName` parameter points to.  
  
 `pcchName`  
 [out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.  
  
 `szName`  
 [out] The buffer that stores the name.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK if the method succeeds; otherwise, E_FAIL or some other error code.  
  
## <a name="requirements"></a>Требования  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [Метод GetSignature](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [Метод GetValue](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
