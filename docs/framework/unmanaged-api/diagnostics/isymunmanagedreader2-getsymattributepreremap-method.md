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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d5702f5df1e2d31a4e01de6be7c70af03b54296
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519688"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>Метод ISymUnmanagedReader2::GetSymAttributePreRemap
Получает настраиваемый атрибут, в зависимости от его имени. В отличие от настраиваемых атрибутов метаданных эти атрибуты хранятся в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `parent`  
 [in] Токен метаданных родительского элемента.  
  
 `name`  
 [in] Указатель на `WCHAR` , содержащее имя.  
  
 `cBuffer`  
 [in] Объект `ULONG32` указывает размер `buffer` массива.  
  
 `pcBuffer`  
 [out] Указатель на `ULONG32` , получающий размер буфера должен содержать атрибут байты.  
  
 `buffer`  
 [out] Указатель на буфер, куда помещаются байты атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
