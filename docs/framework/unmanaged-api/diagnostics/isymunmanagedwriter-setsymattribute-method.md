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
ms.openlocfilehash: ab637b33797ebc5b6d16873cb460c465405b6849
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645656"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>Метод ISymUnmanagedWriter::SetSymAttribute
Определяет настраиваемый атрибут, в зависимости от его имени. Эти атрибуты хранятся в хранилище символов, в отличие от настраиваемых атрибутов метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `parent`  
 [in] Токен метаданных, для которого определен атрибут.  
  
 `name`  
 [in] Указатель на `WCHAR` , содержащий имя атрибута.  
  
 `cData`  
 [in] Объект `ULONG32` указывает размер `data` массива.  
  
 `data`  
 [in] Значение атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
