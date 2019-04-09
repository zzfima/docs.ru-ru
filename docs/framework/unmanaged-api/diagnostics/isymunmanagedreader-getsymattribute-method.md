---
title: Метод ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89831261c5da156343cb098ace715495ddafccaf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086095"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>Метод ISymUnmanagedReader::GetSymAttribute
Получает настраиваемый атрибут, в зависимости от его имени. В отличие от настраиваемых атрибутов метаданных эти настраиваемые атрибуты хранятся в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `parent`  
 [in] Токен метаданных для объекта, для которого запрашивается этот атрибут.  
  
 `name`  
 [in] Указатель на переменную, которая указывает извлекаемого атрибута.  
  
 `cBuffer`  
 [in] Размер массива `buffer`.  
  
 `pcBuffer`  
 [out] Указатель на переменную, которая получает длину данных атрибута.  
  
 `buffer`  
 [out] Указатель на переменную, которая получает данные атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
