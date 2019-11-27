---
title: Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: 393984241412f543b6ac082484cf5e23edb2d9f4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448980"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2
Позволяет компилятору опускать функции, которые не были изменены из потока базы данных программы (PDB), при условии, что сведения о строке соответствуют требованиям. Правильная информация о строке может быть определена со старыми сведениями о строке PDB и одной разностью для всех строк в функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a>Параметры  
 `pIStream`  
 окне Указатель на объект [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , содержащий сведения о строке.  
  
 `pDeltaLines`  
 окне Указатель на структуру [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) , содержащую измененные строки.  
  
 `cDeltaLines`  
 окне `ULONG`, представляющая число измененных строк.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
