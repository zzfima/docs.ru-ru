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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0ce6a207f2a7862b0b49f1e68cda9528aa03ca7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667535"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>Метод ISymUnmanagedWriter2::DefineLocalVariable2
Определяет одну переменную в текущей лексической области видимости. Этот метод может вызываться несколько раз для переменной с тем же именем, имеющей несколько корневых в пределах области. В данном случае, однако значения `startOffset` и `endOffset` параметров не должны перекрываться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `name`  
 [in] Имя локальной переменной.  
  
 `attributes`  
 [in] Атрибуты локальной переменной.  
  
 `sigToken`  
 [in] Маркер метаданных для подписи.  
  
 `addrKind`  
 [in] Тип адреса.  
  
 `addr1`  
 [in] Первый адрес для спецификации параметра.  
  
 `addr2`  
 [in] Второй адрес для спецификации параметра.  
  
 `addr3`  
 [in] Третий адрес для спецификации параметра.  
  
 `startOffset`  
 [in] Начальное смещение для переменной. Этот параметр является необязательным. Если задано значение 0, этот параметр игнорируется, и переменная определяется для всей области. Если ненулевое значение, переменная находится в границах смещений текущей области.  
  
 `endOffset`  
 [in] Конечное смещение для переменной. Этот параметр является необязательным. Если задано значение 0, этот параметр игнорируется, и переменная определяется для всей области. Если ненулевое значение, переменная находится в границах смещений текущей области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [Метод DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
