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
ms.openlocfilehash: 7f04b5c100f1fd9c44e671b883fe469b16d33fa6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440137"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>Метод ISymUnmanagedReader::GetSymAttribute
Возвращает настраиваемый атрибут на основе его имени. В отличие от пользовательских атрибутов метаданных эти пользовательские атрибуты хранятся в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне Токен метаданных для объекта, для которого запрашивается атрибут.  
  
 `name`  
 окне Указатель на переменную, которая указывает извлекаемый атрибут.  
  
 `cBuffer`  
 [in] Размер массива `buffer`.  
  
 `pcBuffer`  
 заполняет Указатель на переменную, которая получает длину данных атрибута.  
  
 `buffer`  
 заполняет Указатель на переменную, которая получает данные атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
