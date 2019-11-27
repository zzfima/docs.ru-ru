---
title: Метод ISymUnmanagedWriter::DefineParameter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: bc1b65de026a674a3dff183050a5a205fd7052c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427993"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>Метод ISymUnmanagedWriter::DefineParameter
Определяет один параметр в текущем методе. Тип параметра берется из расположения параметра (Sequence) в сигнатуре метода.  
  
 Если в метаданных для данного метода определены параметры, их не нужно определять повторно с помощью этого метода. Прежде чем проверять хранилище символов, средства чтения символов должны проверить обычные метаданные для параметров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 окне Имя параметра.  
  
 `attributes`  
 окне Атрибуты параметра.  
  
 `sequence`  
 окне Сигнатура параметра.  
  
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
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
