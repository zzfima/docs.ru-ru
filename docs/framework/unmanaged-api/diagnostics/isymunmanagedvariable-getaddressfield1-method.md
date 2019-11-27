---
title: Метод ISymUnmanagedVariable::GetAddressField1
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: a59b50009e7f0ab2fff1b8439e368234403822c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446134"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a>Метод ISymUnmanagedVariable::GetAddressField1
Возвращает первое поле адреса для этой переменной. Его значение зависит от типа адреса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRetVal`  
 заполняет Указатель на `ULONG32`, который получает первое поле адреса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [Метод GetAddressField2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [Метод GetAddressField3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [Метод GetAddressKind](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
