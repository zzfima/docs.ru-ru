---
title: Метод ISymUnmanagedWriter::SetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4450c262b75a73114cb7de7de98567f053bbf564
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894464"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>Метод ISymUnmanagedWriter::SetSymAttribute
Определяет настраиваемый атрибут на основе его имени. Эти атрибуты хранятся в хранилище символов в отличие от пользовательских атрибутов метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `parent`  
 окне Токен метаданных, для которого определяется атрибут.  
  
 `name`  
 окне Указатель на объект `WCHAR` , содержащий имя атрибута.  
  
 `cData`  
 окне Значение `ULONG32` типа, указывающее размер `data` массива.  
  
 `data`  
 окне Значение атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
