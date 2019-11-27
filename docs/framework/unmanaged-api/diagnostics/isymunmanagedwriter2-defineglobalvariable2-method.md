---
title: Метод ISymUnmanagedWriter2::DefineGlobalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: 12475b1ac8a1a81e565aa689eac2ae1a9b55e73a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438283"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>Метод ISymUnmanagedWriter2::DefineGlobalVariable2
Определяет одну глобальную переменную.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 окне Имя глобальной переменной.  
  
 `attributes`  
 окне Атрибуты глобальных переменных.  
  
 `sigToken`  
 окне Маркер метаданных сигнатуры.  
  
 `addrKind`  
 окне Тип адреса.  
  
 `addr1`  
 окне Первый адрес для спецификации параметра.  
  
 `addr2`  
 окне Второй адрес для спецификации параметра.  
  
 `addr3`  
 окне Третий адрес для спецификации параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [Метод DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
