---
title: Метод ISymUnmanagedReader2::GetSymAttributePreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: 4009f8988c90ed090c0cc3d86164af347055722f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446418"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>Метод ISymUnmanagedReader2::GetSymAttributePreRemap
Возвращает настраиваемый атрибут на основе его имени. В отличие от пользовательских атрибутов метаданных эти атрибуты хранятся в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `parent`  
 окне Маркер метаданных родителя.  
  
 `name`  
 окне Указатель на `WCHAR`, содержащий имя.  
  
 `cBuffer`  
 окне `ULONG32`, указывающий размер массива `buffer`.  
  
 `pcBuffer`  
 заполняет Указатель на `ULONG32`, который получает размер буфера, необходимый для хранения байтов атрибута.  
  
 `buffer`  
 заполняет Указатель на буфер, который получает байты атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
