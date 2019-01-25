---
title: Метод ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03c0a9d7315f5158948701d4322887104f0844c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603668"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>Метод ISymUnmanagedWriter::DefineField
Определяет одну переменную, не внутри метода. Этот метод является, используемых для некоторых полей в классах, битовые поля и т. д.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>Параметры  
 `parent`  
 [in] Метаданные типа или метода токена.  
  
 `name`  
 [in] Имя поля.  
  
 `attributes`  
 [in] Атрибуты поля.  
  
 `cSig`  
 [in] Объект `ULONG32` то есть размер в символах, буфера, требуемого для хранения подпись поля.  
  
 `signature`  
 [in] Массив полей подписи.  
  
 `addrKind`  
 [in] Тип адреса.  
  
 `addr1`  
 [in] Первый адрес для спецификации поля.  
  
 `addr2`  
 [in] Второй адрес для спецификации поля.  
  
 `addr3`  
 [in] Третий адрес для спецификации поля.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
