---
title: Метод ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 923a92ea256f79a1b0130b61c4fd99460fda96a0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441808"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>Метод ISymUnmanagedReader::GetMethodsFromDocumentPosition
Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `document`  
 окне Указанный документ.  
  
 `line`  
 окне Строка указанного документа.  
  
 `column`  
 окне Столбец указанного документа.  
  
 `cMethod`  
 [in] Размер массива `pRetVal`.  
  
 `pcMethod`  
 заполняет Указатель на переменную, которая получает количество элементов, возвращенных в массиве `pRetVal`.  
  
 `pRetVal`  
 заполняет Массив указателей, каждый из которых указывает на объект [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) , представляющий метод, содержащий точку останова.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
