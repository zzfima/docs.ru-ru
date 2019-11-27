---
title: Метод ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 264b4487483ed5439a9809feefcdc1b20af402dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428079"
---
# <a name="isymunmanagedwriterclosescope-method"></a>Метод ISymUnmanagedWriter::CloseScope
Закрывает текущую лексическую область видимости.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `endOffset`  
 окне Смещение от начала метода точки в конце последней инструкции в лексической области в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="remarks"></a>Примечания  
 После закрытия области в ней больше нельзя определять переменные.  
  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, который можно использовать с [ISymUnmanagedWriter:: сетскоперанже](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) , чтобы определить начальное и конечное смещение области. В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются. Идентификаторы областей допустимы только в текущем методе.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
