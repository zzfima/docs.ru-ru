---
title: Метод ISymUnmanagedWriter2::DefineLocalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: 73f536b4ab98aa596c2395810cb8b616ffd309e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438295"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>Метод ISymUnmanagedWriter2::DefineLocalVariable2
Определяет одну переменную в текущей лексической области видимости. Этот метод может вызываться несколько раз для переменной с тем же именем, которая имеет несколько домов в пределах области. Однако в этом случае значения параметров `startOffset` и `endOffset` не должны перекрываться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 окне Имя локальной переменной.  
  
 `attributes`  
 окне Атрибуты локальной переменной.  
  
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
  
 `startOffset`  
 окне Начальное смещение для переменной. Этот параметр является необязательным. Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью. Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.  
  
 `endOffset`  
 окне Конечное смещение для переменной. Этот параметр является необязательным. Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью. Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [Метод DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
